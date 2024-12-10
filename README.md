# Flipkart Mobile Scraper

## Overview
This project is a web scraper designed to extract mobile phone data from Flipkart. The scraper gathers information such as product names, prices, storage capacity, display size, camera details, battery capacity, ratings, processor details, warranty information, and overall reviews. The collected data is saved into a CSV file for further analysis.

## Features
- Rotates User-Agent strings to avoid detection and blocking.
- Uses a random delay between requests to mimic human behavior.
- Handles potential request errors and ensures data consistency.
- Extracts multiple details about mobile phones from Flipkart.

## Requirements
- Python 3.x
- Requests library
- BeautifulSoup library
- Pandas library

## Installation
1. Clone the repository:
    ```sh
    git clone https://github.com/yourusername/flipkart-mobile-scraper.git
    cd flipkart-mobile-scraper
    ```

2. Install the required Python libraries:
    ```sh
    pip install -r requirements.txt
    ```

## Usage
1. Open the script `flipkart_scraper.py` and set the URL for the desired product search on Flipkart.
2. Run the script:
    ```sh
    python flipkart_scraper.py
    ```

3. The data will be saved to a CSV file named `flipkart_mobile_data.csv` in the same directory.

## Script Details
### Libraries
- `requests`: For sending HTTP requests.
- `BeautifulSoup`: For parsing HTML content.
- `pandas`: For handling data and saving it into a CSV file.
- `time` and `random`: For implementing delays and randomizing headers.

### Functions
- `get_random_headers()`: Returns random headers for the requests to avoid detection.
- `ensure_length(data_list, target_length, fill_value)`: Ensures all lists have the same length by filling missing values.
- `scrape_page(page_number)`: Scrapes a single page of search results and appends the extracted data to corresponding lists.

### Process
1. The script iterates through a predefined number of pages, sending requests to Flipkart's search results page.
2. Parses the HTML content to extract product details.
3. Appends the extracted data to lists.
4. Ensures all lists have the same length to avoid issues when creating a DataFrame.
5. Saves the data into a CSV file.

## Customization
- **URL**: Change the URL in the `scrape_page` function to target a different search query on Flipkart.
- **Number of Pages**: Adjust the `num_pages` variable to scrape more or fewer pages.
- **Proxy**: Add your proxy details in the `proxies` dictionary if needed.

## Error Handling
The script includes basic error handling to manage request failures and parsing issues. It prints an error message and skips to the next page if a request fails.

## Notes
- Ensure compliance with Flipkart's terms of service when scraping data.
- Use the scraper responsibly to avoid overloading the website's servers.

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.

## Acknowledgments
Special thanks to the developers of the Requests, BeautifulSoup, and Pandas libraries for making web scraping and data handling in Python easier.
