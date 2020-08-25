# GSoC Final Report
#### Organization : International Neuroinformatics Coordinating Facility (INCF)
##### Project      : Automated comparison of scientific methods for time series analysis.
##### Student      : Salman Khan
##### Mentors      : Ben Fulcher, Oliver Cliff, Joseph Lizier

### Introduction

In this **Google Summer of Code 2020** project I developed a web-based system that helps the user to compare new time-series analysis algorithms to a collection of over 7700 existing algorithms, implemented as the [_hctsa_ package](https://github.com/benfulcher/hctsa).
The website takes a new time-series analysis algorithm (as python code) from the user and computes its outputs across a [dataset of 1000 diverse time series](https://figshare.com/articles/1000_Empirical_Time_series/5436136).
It then analyzes the correlation between the output of the user's algorithm with the _hctsa_ feature library and presents a range of intuitive output visualizations that show the best-matching features.
This output helps the user to understand connections between their method and the existing interdisciplinary time-series analysis literature, and therefore to assess whether their algorithm is really contributing progress to the literature.

Here is an example of the website functionality I developed from scratch in this GSoC project:![](GIF-200821_144005.gif)

1. First phase - **Backend / logic development**  
&nbsp; _I developed a series of functions to enable successful execution of the user's code, and to perform systematic comparison of its output to that of existing algorithms:_  

   * Read the user's code as a string to check for malicious code before execution  
   * Passes a diverse time-series dataset through user's function and generate long feature vector.
   * Compute the Spearman correlation coefficient between the computed feature vector and with every individual _hctsa_ feature, and sort and store all of the relevant information: (Feature name, Keywords, _p_-value, Correlation coefficient).  

2. Second phase - **Front-end development**  
&nbsp; _In this phase, I focused on front-end development, that will be used by the user.
I implemented a range of functionality, including:_  
  

   * Development of pages for websites, including 'Home', 'How-it-works', 'Contact', 'Preloader', 'Result', 'Syntax error', 'Timeout Error', and '404 Not found'.  
   
   * Interactive results table (functionality shown in the gif below), that allows users to:  
      * Toggle to change representation of results.
      * Download all results in .csv format.
      * Toggle button to view table in full size.
      * Choose show / hide column from table:![](GIF-200822_154604[1].gif)  
      
   * Visualization of top 12 results as interactive scatter plots (as visualized in the gif below), which enables users to:  
      * Hover to see data points.
      * Zoom each plot or all subplots simultaneously to more clearly visualize the relationships.![](GIF-200822_154727[1].gif)  
   * Visualization of pairwise relationships between each of the top 12 matches as a correlation heatmap reordered using linkage clustering.  
   
3. Third phase - **Running user's code securely and with error handling.**  
&nbsp; _This was one of the major challenges, as executing custom user code on a server could compromise the system.Thus, in order to run user's code safely, we:_  
  
   * Used RestrictedPython to run the user's code in a restricted environment.
   * Allow the user to import only specific modules that are relevant to scientific data analysis, and thus disabling functionality related to accessing/modifying the system.
   * Restricted in-built functions like exec or eval that could be used to harm the system.
   * Added a timeout limit so that the system is protected from algorithms falling into an infinite loop. 


### Link to work  
   * [Link to full repository](#)
   * [Links for all commits](#)

