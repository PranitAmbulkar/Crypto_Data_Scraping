# Crypto_Data_Scraping
This is the code to scrape the real time data for the top 20 cryptocurrencies from Mudrex.com
Following is the link for google sheet where the actual real time data is updating = https://docs.google.com/spreadsheets/d/1SjPhBvUXrVEDqPB3ug2OD4-8WCk_4E64YSCcxI_X3qs/edit?usp=sharing

These are the libraries imported for various functionalities:

    requests: Used to send HTTP requests to Mudrex website and get the HTML content.
    BeautifulSoup: Used to parse the HTML content and extract data.
    gspread: Used to interact with Google Sheets API.
    ServiceAccountCredentials: Used for authentication with Google Sheets API using service account credentials.
    sleep: Used to pause the execution of the script for a specified amount of time.

Function scrape_mudrex()
This function scrapes real-time price data for the top 20 cryptocurrencies from the Mudrex website. It sends an HTTP GET request to the URL, parses the HTML content using BeautifulSoup, finds the table containing cryptocurrency data, iterates through the rows of the table (excluding the header row), extracts the cryptocurrency name and price, and stores them in a dictionary.

Function update_google_sheet()
This function updates a Google Sheet with the scraped cryptocurrency data. It authenticates with the Google Sheets API using service account credentials, opens the specified Google Sheet, clears existing data, appends a header row with column names 'Cryptocurrency' and 'Price', and then appends each cryptocurrency name and price as a new row in the sheet.

Main Function
The main function continuously scrapes data from Mudrex, updates the Google Sheet, and then waits for one minute before repeating the process. This loop ensures that the Google Sheet stays updated with the latest cryptocurrency prices from Mudrex.
