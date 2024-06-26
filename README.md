### Project Overview

This script accomplishes the following tasks:

* Data Input: Reads company names and URLs from a designated Google Sheet.
* Data Scraping: Scrapes essential content from each company's homepage using Python libraries.
* Data Cleaning: Removes HTML tags, navigation elements, and advertisements from the scraped content.
* Data Storage: Stores the cleaned data in a new sheet within the same Google Sheet document.
* AI Processing: Uses OpenAI's API to run a sequence of three prompts on the cleaned data.
* Output Storage: Stores the outputs from each prompt in separate columns of the Google Sheet.

### Requirements

Python 3.x


**Required Libraries:**
* requests
* beautifulsoup4
* nltk
* pandas
* gspread
* cohere
* Instructions


### Set Up

* using google cloud services create  a service account and get its credentials in json format
* Copy Url of google sheets and make sure to get sheet number of both one with prompt and one which is supposed to be scrapped
* Get client key from Cohere 
* Make sure to share google spreadsheet with service account
* Initiate function  final_automation() with its parameters to update the sheet


### functions

* create_df(url , sheet_number): ->dataframe : convert url and sheet number to pd dataframe
* clean_scrapedtext(html)->string : convert scraped html from website to cleaned format
* scrape(URL)->string : scraps website
* new_col(df , col_name) : update dataframe by adding scrapped data
* preprocess(text)->string : preprocess text
*  workflow(url , sheet_number , col_name , prompt_sheet_number): Initiate while workflow
* final_automation(url , json , client_key , sheet_number , col_name , prompt_sheet_number) : Automate everything from authentication to workflow ending
* Prompt1 , Prompt2 , Prompt3 : Provide results of prompt with same name
