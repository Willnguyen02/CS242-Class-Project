Running the WikiLaw Crawler

## Project Structure
wiki_spider.py: The core Scrapy spider containing the scraping logic and settings.

crawler.bat: Windows executable script to run the crawler with parameters.

seed.txt: A text file containing the starting URL(s).

## Deployment Instructions
1. Prerequisites
Install the scrapy library

PowerShell
pip install scrapy


2. Setup the Seed File
Create a file named seed.txt in the root directory and add the starting URL:

Plaintext
https://en.wikipedia.org/wiki/Law

3. Execution
Run the crawler using the provided batch file. Open your terminal in the project folder and use the following syntax:  

Command Syntax:   

PowerShell   
.\crawler.bat <seed-file> <num-pages> <hops-away> <output-dir>   

Example Command: To crawl 100,000 pages and save them to a folder named output, run:   
PowerShell
.\crawler.bat seed.txt 100000 6 .\output

## Output
The results are saved in jsonlines format within the specified output directory. Each entry contains:

url: The source link.

title: The flat-string title of the Wikipedia article.

text: Cleaned, whitespace-normalized body text.