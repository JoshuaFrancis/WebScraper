# WebScraper
Web Scraper README

Overview

This Python script is a web scraper designed to extract data from websites, including tables, paragraphs, headings, and links. The extracted data is saved to a CSV file for easy analysis and storage. It supports multiple pages by automatically following "Next" links.

Features

Fetches and parses HTML content from a given URL.
Extracts tables, paragraphs, headings, and links from the page.
Saves the extracted data to a CSV file.
Automatically follows "Next" page links to scrape multiple pages.
Validates and ensures the URL uses HTTPS.
Prerequisites

Python 3.6 or higher
Required Python packages: requests, beautifulsoup4, csv, logging
Installation

Clone the repository or download the script file.

bash
Copy code
git clone <repository_url>
cd <repository_directory>
Install the required packages.

bash
Copy code
pip install requests beautifulsoup4
Usage

Run the script.

bash
Copy code
python scraper.py
Enter the URL of the website you wish to scrape when prompted.

Code Structure

1. scrape_page(url)
Fetches the content of the page at the given URL and returns a BeautifulSoup object.

Parameters: url - The URL of the page to scrape.
Returns: BeautifulSoup object containing the page content.
2. extract_data(soup)
Extracts various types of data from the BeautifulSoup object.

Parameters: soup - BeautifulSoup object of the page.
Returns: Dictionary containing extracted tables, paragraphs, headings, and links.
3. save_to_csv(data, filename='output.csv')
Saves the extracted data to a CSV file.

Parameters:
data - Dictionary containing data to save.
filename - Name of the output CSV file (default is output.csv).
4. find_next_page(soup, base_url)
Finds the URL of the next page.

Parameters:
soup - BeautifulSoup object of the page.
base_url - Base URL to resolve relative links.
Returns: URL of the next page or None if not found.
5. scrape_website(url)
Scrapes the website starting from the given URL and saves the data to a CSV file.

Parameters: url - The initial URL of the website to scrape.
6. is_valid_url(url)
Validates the given URL and ensures it uses HTTPS.

Parameters: url - URL to validate.
Returns: Valid HTTPS URL or None if invalid.
7. __main__
Main function that prompts the user for a URL and initiates the scraping process.

Logging

The script uses the logging module to log informational messages and errors. Logs include:

Initial page content.
Extracted data.
Status of saving data to CSV.
Errors encountered during HTTP requests or file operations.
Examples

Example 1: Scraping a Single Page
To scrape a single page, simply run the script and enter the URL when prompted. The script will extract the data and save it to output.csv.

Example 2: Scraping Multiple Pages
If the website has a "Next" link, the script will follow it to scrape additional pages, combining all data into output.csv.

Notes

Ensure the website you are scraping allows automated access in its robots.txt file.
Use a valid User-Agent string to avoid being blocked by websites.
Adjust the script for specific websites if the data extraction logic does not meet your needs.
