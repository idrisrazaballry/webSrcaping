# Web Scraping Projects

This repository contains two web scraping exercises demonstrating both **static** and **dynamic** web scraping techniques in Python.

## 📁 Project Structure

```
web scraping/
├── day1.ipynb            # Static web scraping (BeautifulSoup)
├── flipkart.ipynb         # Dynamic web scraping (Selenium)
├── books.xlsx             # Output: scraped book data
└── smasung_mobile.xlsx    # Output: scraped Samsung mobile data
```

## 📘 1. Static Web Page Scraping — `day1.ipynb`

Scrapes book details from [books.toscrape.com](https://books.toscrape.com/) using `requests` and `BeautifulSoup`.

**What it does:**
- Sends an HTTP GET request to fetch the page's HTML content
- Parses the HTML using `BeautifulSoup`
- Extracts individual book names, then all book names on a page
- Extracts book prices
- Loops through all 50 catalogue pages to collect:
  - Book names
  - Prices
  - Ratings
  - Stock availability
- Saves the final dataset to `books.xlsx` using `pandas`

**Libraries used:** `requests`, `beautifulsoup4`, `pandas`, `openpyxl`

## 📱 2. Dynamic Web Page Scraping — `flipkart.ipynb`

Scrapes Samsung mobile listings from [Flipkart](https://www.flipkart.com/) using `Selenium`, since the page content is rendered dynamically via JavaScript.

**What it does:**
- Launches a Chrome browser session with Selenium's WebDriver
- Navigates to Flipkart and closes the login pop-up
- Searches for **"samsung mobiles"** using the search bar
- Extracts mobile names and prices from the search results
- Clicks the "Next" button to paginate through multiple pages of results
- Compiles all scraped data and saves it to `smasung_mobile.xlsx` using `pandas`

**Libraries used:** `selenium`, `pandas`, `openpyxl`

## ⚙️ Requirements

```
pip install requests beautifulsoup4 pandas openpyxl selenium
```

For `flipkart.ipynb`, you'll also need:
- [Google Chrome](https://www.google.com/chrome/) installed
- ChromeDriver matching your Chrome version (or use `webdriver-manager` to handle this automatically)

## ▶️ How to Run

1. Install the required libraries above.
2. Open the notebooks in Jupyter Notebook / JupyterLab / VS Code.
3. Run `day1.ipynb` for static scraping (books data).
4. Run `flipkart.ipynb` for dynamic scraping (Samsung mobiles data).
5. Output files (`books.xlsx`, `smasung_mobile.xlsx`) will be generated in the project folder.

## 📊 Output

| File | Description |
|------|-------------|
| `books.xlsx` | Book names, prices, ratings, and stock availability from all 50 pages of books.toscrape.com |
| `smasung_mobile.xlsx` | Samsung mobile names and prices scraped from Flipkart search results |

## 🧠 Key Concepts Practiced

- Static vs. dynamic web scraping
- HTML parsing with BeautifulSoup (`find`, `find_all`, tag attributes)
- Browser automation with Selenium (`find_element`, `find_elements`, clicks, key input)
- Pagination handling in both scraping methods
- Exporting scraped data to Excel using pandas

