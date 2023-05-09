# websites_extraction
In this repository there are files are part of the Thesis: <br>
[Automating the data acquisition of Businesses and their actions regarding environmental sustainability: The Energy Industry in Greece](Thesis_DI_Format%20(1).pdf)



Parts of the data engineering process that is described in the thesis file, written in Python, that all together consist the pipeline of the procedure shown in the image below:
![Pipeline](pipeline.jpg)


## Pipeline
The steps are the following:
1. Use a crawler algorithm to exract a **list** of all the Greek businesses that belong to the energy factor with their domains (source www.dnb.com)
2. Use a crawler algorithm that will look over all the HTML of each and every domain in our **list** as well as all the URLs appearing on these web pages and its subdomains & will extract their content (HTML files). Moreover it will extract pdf files refering to ESG factors using a _customizing_ dictionary of words as an content-filter method [ESG Dictionary](websites_extraction/esg_dict.csv)
 (script related &rightarrow; crawler_pdfs.py)
3. Use a boiler plate removal algorithm that removes HTML syntax and keep only the text (not publicly available in the repository)
4. Evaluate web-scrapping process defining & calculating specific metrics. Exports the results in a csv (script related &rightarrow; meta_cleaning_2.py)

* There is also available a script of the crawler designed to read local HTML files (instead of URLs as decribed in step 2), in order to extract ESG pdf files. (script related &rightarrow; Crawler_pdfs_from_html_files.py)

## How to run
- Crawler_pdfs_from_html_files.py <br>
   In order to run the script, user needs to give as input: 
    1. The input path that contains folders per website under which there are stored all HTML files (Input parameter parameter: _--inpath_) <br> (e.g. --inpath C:\Users\userXXX\Downloads\thesis\inp) <br> 
    2. The output path that user desires to store the results (ESG/Sustainability pdf files) per website  (Input parameter parameter: _--out_dir_) <br> (e.g. --out_dir C:\Users\userXXX\Downloads\thesis\out) <br> 

Optional feature:
After first run a (default) dictionary for words of interest ([ESG Dictionary](websites_extraction/esg_dict.csv)) is generated at input forlder so that user can maintain it. 


