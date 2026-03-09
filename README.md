E-Commerce Competitive Intelligence: Music Category
Web Scraping & Exploratory Data Analysis (EDA) Pipeline

Project Purpose
This project simulates a Competitive Intelligence task. I developed a Python-based ETL pipeline to monitor competitor pricing, inventory levels, and product ratings. Instead of using a pre-cleaned dataset, I extracted "live" data from a web sandbox to demonstrate my ability to handle unstructured data and real-world encoding challenges.

The "Analyst" Workflow
I approached this project in three distinct phases:

1. Extraction (The Scraper)
Gallery Scraping: Collected high-level data (Title, Price, Rating) from the main category page.

Deep Crawling: Programmatically followed internal links to visit each product's unique page.

Table Parsing: Extracted technical specifications from HTML tables that are not visible on the main search results.

2. Transformation (Data Wrangling)
Regex Cleaning: Used Regular Expressions to strip currency symbols and fix UTF-8 encoding artifacts (the Â£ issue).

Type Conversion: Cast string-based prices and ratings into float and int formats for mathematical analysis.

Data Merging: Performed a Left Join (using Pandas) to combine surface data with deep-scraped technical specs.

3. Analysis & Visualization
Calculated Tax Percentages to verify pricing consistency.

Analyzed Stock Availability to identify potential supply chain gaps.

Visualized the Rating Distribution to assess inventory quality.

Data Dictionary
Providing a dictionary shows recruiters you understand how to document data for other stakeholders.

Column Name,Type,Description
Title,String,Full name of the book.
UPC,String,Universal Product Code (Unique ID).
Price,Float,Final consumer price in GBP (£).
Tax,Float,Tax amount applied to the product.
Rating_Num,Integer,Numerical representation of star rating (1-5).
Availability,Integer,Physical units currently in stock.

Key Findings
Pricing Accuracy: The scraper successfully identified that a flat tax rate is applied across the entire Music category.

Data Integrity: By utilizing re (Regular Expressions), I achieved a 0% failure rate in price conversion despite inconsistent HTML formatting.

How to Use
Prerequisites: Ensure you have Python installed.

Install Libraries: pip install pandas beautifulsoup4 requests seaborn matplotlib

Run: Execute web_scraping.ipynb to regenerate the music_books_analysis.csv file.
