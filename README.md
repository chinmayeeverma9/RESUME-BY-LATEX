\documentclass[10pt, letterpaper]{article}

% Packages:
\usepackage[
    ignoreheadfoot, % set margins without considering header and footer
    top=0.5 cm, % seperation between body and page edge from the top
    bottom=1 cm, % seperation between body and page edge from the bottom
    left=1 cm, % seperation between body and page edge from the left
    right=1 cm, % seperation between body and page edge from the right
    footskip=1.0 cm, % seperation between body and footer
    % showframe % for debugging 
]{geometry} % for adjusting page geometry
\usepackage{titlesec} % for customizing section titles
\usepackage{tabularx} % for making tables with fixed width columns
\usepackage{array} % tabularx requires this
\usepackage[dvipsnames]{xcolor} % for coloring text
\definecolor{primaryColor}{RGB}{0, 0, 0} % define primary color
\usepackage{enumitem} % for customizing lists
\usepackage{fontawesome5} % for using icons
\usepackage{amsmath} % for math
\usepackage[
    pdftitle={Chinmayee Verma CV},
    pdfauthor={Chinmayee },
    pdfcreator={LaTeX with RenderCV},
    colorlinks=true,
    urlcolor=primaryColor
]{hyperref} % for links, metadata and bookmarks
\usepackage[pscoord]{eso-pic} % for floating text on the page
\usepackage{calc} % for calculating lengths
\usepackage{bookmark} % for bookmarks
\usepackage{lastpage} % for getting the total number of pages
\usepackage{changepage} % for one column entries (adjustwidth environment)
\usepackage{paracol} % for two and three column entries
\usepackage{ifthen} % for conditional statements
\usepackage{needspace} % for avoiding page brake right after the section title
\usepackage{iftex} % check if engine is pdflatex, xetex or luatex

% Ensure that generate pdf is machine readable/ATS parsable:
\ifPDFTeX
    \input{glyphtounicode}
    \pdfgentounicode=1
    \usepackage[T1]{fontenc}
    \usepackage[utf8]{inputenc}
    \usepackage{lmodern}
\fi

\usepackage{charter}

% Some settings:
\raggedright
\AtBeginEnvironment{adjustwidth}{\partopsep0pt} % remove space before adjustwidth environment
\pagestyle{empty} % no header or footer
\setcounter{secnumdepth}{0} % no section numbering
\setlength{\parindent}{0pt} % no indentation
\setlength{\topskip}{0pt} % no top skip
\setlength{\columnsep}{0.15cm} % set column seperation
\pagenumbering{gobble} % no page numbering

\titleformat{\section}{\needspace{4\baselineskip}\bfseries\large}{}{0pt}{}[\vspace{1pt}\titlerule]

\titlespacing{\section}{
    % left space:
    -1pt
}{
    % top space:
    0.3 cm
}{
    % bottom space:
    0.2 cm
} % section title spacing

\renewcommand\labelitemi{$\vcenter{\hbox{\small$\bullet$}}$} % custom bullet points
\newenvironment{highlights}{
    \begin{itemize}[
        topsep=0.10 cm,
        parsep=0.10 cm,
        partopsep=0pt,
        itemsep=0pt,
        leftmargin=0 cm + 10pt
    ]
}{
    \end{itemize}
} % new environment for highlights


\newenvironment{highlightsforbulletentries}{
    \begin{itemize}[
        topsep=0.10 cm,
        parsep=0.10 cm,
        partopsep=0pt,
        itemsep=0pt,
        leftmargin=10pt
    ]
}{
    \end{itemize}
} % new environment for highlights for bullet entries

\newenvironment{onecolentry}{
    \begin{adjustwidth}{
        0 cm + 0.00001 cm
    }{
        0 cm + 0.00001 cm
    }
}{
    \end{adjustwidth}
} % new environment for one column entries

\newenvironment{twocolentry}[2][]{
    \onecolentry
    \def\secondColumn{#2}
    \setcolumnwidth{\fill, 4.5 cm}
    \begin{paracol}{2}
}{
    \switchcolumn \raggedleft \secondColumn
    \end{paracol}
    \endonecolentry
} % new environment for two column entries

\newenvironment{threecolentry}[3][]{
    \onecolentry
    \def\thirdColumn{#3}
    \setcolumnwidth{, \fill, 4.5 cm}
    \begin{paracol}{3}
    {\raggedright #2} \switchcolumn
}{
    \switchcolumn \raggedleft \thirdColumn
    \end{paracol}
    \endonecolentry
} % new environment for three column entries

\newenvironment{header}{
    \setlength{\topsep}{0pt}\par\kern\topsep\centering\linespread{1.5}
}{
    \par\kern\topsep
} % new environment for the header

\newcommand{\placelastupdatedtext}{% \placetextbox{<horizontal pos>}{<vertical pos>}{<stuff>}
  \AddToShipoutPictureFG*{% Add <stuff> to current page foreground
    \put(
        \LenToUnit{\paperwidth-2 cm-0 cm+0.05cm},
        \LenToUnit{\paperheight-1.0 cm}
    ){\vtop{{\null}\makebox[0pt][c]{
        \small\color{gray}\textit{Last updated in July 2024}\hspace{\widthof{Last updated in July 2024}}
    }}}%
  }%
}%

% save the original href command in a new command:
\let\hrefWithoutArrow\href

% new command for external links:


\begin{document}
    \newcommand{\AND}{\unskip
        \cleaders\copy\ANDbox\hskip\wd\ANDbox
        \ignorespaces
    }
    \newsavebox\ANDbox
    \sbox\ANDbox{$|$}

    \begin{header}
        \fontsize{25 pt}{25 pt}\selectfont Chinmayee Verma

        \vspace{5 pt}

        \normalsize
      %  \mbox{Chhattisgarh}%
      %  \kern 5.0 pt%
        \AND
        \kern 5.0 pt%
        \mbox{\hrefWithoutArrow{mailto:youremail@yourdomain.com}{chinmayeeverma9@gmail.com}}%
        \kern 5.0 pt%
        \AND%
        \kern 5.0 pt%
        \mbox{\hrefWithoutArrow{tel:+91-920-100-32-19}{+91-9201003219}}%
        
        \kern 5.0 pt%
        \AND
        \kern 5.0 pt%
        \mbox LinkedIn: {\hrefWithoutArrow{www.linkedin.com/in/chinmayee-verma

 }{\bf Chinmayee Verma}}%
        \kern 5.0 pt%
        \AND%
        \kern 5.0 pt%
        \mbox Github: {\hrefWithoutArrow{https://github.com/chinmayeeverma9}{\bf chinmayeeverma9}}%
    \end{header}

    \vspace{5 pt - 0.3 cm}


    \section{Profile}



        
        \begin{onecolentry}
            Aspiring Data Scientist and Business Analyst proficient in Python, R, SQL, and Excel. Experienced in data cleaning, exploratory data analysis, and leveraging machine learning tools to uncover insights and drive business decisions.  

 \href{https://github.com/sinaatalay/rendercv}{
        \end{onecolentry}

  \section{Skills}


\begin{onecolentry}
            \textbf{Technical Skills:} EDA, Supervised Learning, Unsupervised Learning, Linear Regression, Logistic Regression, NLP. 
        \end{onecolentry}

        \vspace{0.1 cm}

        
        \begin{onecolentry}
            \textbf{Languages:} SQL, Python, R, C++, C, Java
        \end{onecolentry}

        \vspace{0.1 cm}

        \begin{onecolentry}
            \textbf{Software:} Excel, Tableau, Power BI,  GitHub, Google Co-lab, Posit Cloud 
        \end{onecolentry}
    
    
    \section{Experience}



        
        \begin{twocolentry}{
            July 2024 - Present }
            \textbf{Machine Learning Intern},   Pratnik infotech \end{twocolentry}

        \vspace{0.10 cm}
        \begin{onecolentry}
            \begin{highlights}
    \item Developed an NLP model to automate customer support, achieving 85\% text classification accuracy.
    \item Preprocessed and categorized customer inquiries, enhancing response efficiency by 20\%.
    \item Evaluated model performance and provided recommendations for automated response systems.  
            \end{highlights}
        \end{onecolentry}
 


        \begin{twocolentry}{
            Feb 2024 - April 2024 
        }
            \textbf{Data Analyst Intern}, Epiassist \end{twocolentry}

        \vspace{0.10 cm}
        \begin{onecolentry}
            \begin{highlights}
    \item Utilized R, Python, SQL, and Excel for data cleaning and manipulation on healthcare datasets.
    \item Conducted exploratory data analysis (EDA) to generate actionable insights and visualizations.
    \item Prepared comprehensive reports that informed decision-making processes. 
            \end{highlights}
        \end{onecolentry}
    
    
    
    \section{Education}
    \begin{twocolentry}{
            Aug 2018 – July 2022
        }
            \textbf{Amity University Rajasthan}, BTech in Biotechnology\end{twocolentry}

        \vspace{0.10 cm}
        \begin{onecolentry}
            \begin{highlights}
                \item CGPA: 8.23/10
    
      \end{highlights}
        \end{onecolentry}


 \section{Certification}
    \begin{onecolentry}{}
             \textbf{}\textit{Machine Learning Specialization by DeepLearningAi (Stanford University)}} \end{onecolentry} 
    \begin{onecolentry}{}
             \textbf{}\textit{Google Data Analytics Professional Certification}}
    }}\end{onecolentry}
   \begin{onecolentry}
             \textbf{}\textit{Python for Everyone by University of Michigan}}\end{onecolentry}

    
    \section{Projects}



        
        \begin{twocolentry}{
            \href{https://github.com/chinmayeeverma9/NLP-for-Customer-Support-Data/tree/main}{Link}}
            \textbf{ \textbf{NLP for Customer Support}}\end{twocolentry}

        \vspace{0.10 cm}
        \begin{onecolentry}
            \begin{highlights}
                \item \textbf { }Enhanced customer support efficiency by implementing NLP algorithms for automated response generation and sentiment analysis, resulting in reduced response times and improved customer satisfaction.

 
                \item Tools Used: Python, NLP, Logistic Regression, Confusion Matrix 
            \end{highlights}
        \end{onecolentry}


        \vspace{0.1 cm}

        \begin{twocolentry}{
            \href{https://github.com/chinmayeeverma9/Credit-Risk-Analytics-Project}{Link}
        }
            \textbf{ \textbf{Credit Risk Analysis using PD model}}\end{twocolentry}

        \vspace{0.10 cm}
        \begin{onecolentry}
            \begin{highlights}
                \item  Develop a Python-based credit risk analysis project using a Probability of Default (PD) model to assess borrowers' creditworthiness. Clean and process data, conduct EDA and implement a fine-tuned supervised learning model. Demonstrate actionable insights and model effectiveness in proactive credit risk management. 
                \item Tools Used: Python, EDA, Logistic Regression, Decision Tree
            \end{highlights}
        \end{onecolentry}


        \vspace{0.1 cm}

        \begin{twocolentry}{
            \href{https://github.com/chinmayeeverma9/Cardiovascular-disease-analysis-through-R}{Link}
        }
            \textbf{Cardiovascular disease EDA using R
}\end{twocolentry}

        \vspace{0.10 cm}
        \begin{onecolentry}
            \begin{highlights}
                \item Explored cardiovascular disease risk factors in adults using R, employing descriptive statistics, correlation analysis, and data visualization, revealing that an active lifestyle reduces risk while high cholesterol, glucose, age, BMI, and MAP increase it.
                \item Tools Used: R, EDA, Statistical Analysis
            \end{highlights}
        \end{onecolentry}



 \section{Additional Information }
\vspace{0.10 cm}
        \begin{onecolentry}
            \begin{highlights}
                \item Open mic as a performer, Model UN, Parliamentary and University level debates, Authored multiple screenplay scripts for Dramatics, Served as the Social Media Coordinator for IEEE AUR, Contributed to the PR team of IEEE AUR. 
            \end{highlights}
        \end{onecolentry}


    

\end{document}
