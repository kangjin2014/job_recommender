# Job Advisor (INACTIVE)

Web scrapping code subjects to the changes of indeed pages. Hence I think the project won't work unless you upgrade the web scraping code. However, the general idea of this project is to use webscraping to collect data and to use elasticsearch as database and matching backend.


![alt text](https://dare2ai.files.wordpress.com/2018/03/screen-shot-2018-03-19-at-11-44-30-pm.png?w=1278)
    
If you dont have resume handy, please download the resumes in the 'sample_resumes' folder to test this web out.

## How to run?

1. Download git and install packages

       $ git clone https://github.com/kangjin2014/job_advisor.git -b devops
       $ pip3 install -r requirements.txt
       
2. Spin up an ElasticSearch database running at port 9200, localhost. Job postings scraped from Indeed will be streamed in. Notice: docker should be installed. 
       
       $ bin/run_elasticsearch.sh

3. Kick off job posting download, streaming the data into elasticsearch server.
        
       $ python3 -m indeed_scraping

4. Spin up a Flask web server which accepts the resume from end users
    
       $ python3 -m flaskr
       
       open the address http://localhost:5000 in the browser
       
       submit the resume by pressing the 'submit' button (support *.doc or *.docx files only)
       
       And will see some recommendation. My suggestion on reference value is based on a small sample study. Will need to impove by machine learning in the future.

:koala: 
