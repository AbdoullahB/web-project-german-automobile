# 🚗 German Automotive Icons

![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white) ![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white) ![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![Data Viz](https://img.shields.io/badge/Data_Viz-Flourish-orange?style=for-the-badge)

## 📖 About the Project
This project was developed as part of the "Web Technologies" course at **Grenoble IAE**.
The goal was to design a complete **Single Page Application (SPA)**, structured and enriched with real-world data regarding the German automotive industry.

It combines historical presentation, technological analysis, and economic data visualization.

![Website Preview](german_auto.png)

## 🐍 Python Automation: Web Scraping
To populate the project with accurate data without manual copying and pasting, I developed a **Python automation script**.

### The Challenge
Collecting lists of car models for multiple manufacturers from Wikipedia is tedious and error-prone when done manually. The URLs always followed the same pattern, but the content varied.

### The Solution
I created a script (`scraper.py`) using **Requests** and **BeautifulSoup** that automates this process.

**Key Features of my Code:**
* **Dynamic URL Parsing:** The script automatically extracts the brand name from the URL using `url.split`.
* **Smart Filtering:** It parses the HTML to retrieve only relevant model links, excluding generic Wikipedia navigation links.
* **CSV Generation:** It automatically creates and names a `.csv` file for each brand (e.g., `BMW_liens.csv`).
* **Interactive Loop:** I implemented a `while True` loop, allowing the user to scrape multiple manufacturers in one session until they type "stop".

```python
# Snippet of the logic used to extract brand names dynamically
def wiki_web_parser(url):
    # Extracts "BMW" from ".../Automobile_BMW"
    marque = url.split("Automobile_")[-1] 
    
    # ... (Request and Parsing logic) ...
    
    print(f"CSV file '{marque}_liens.csv' created successfully!")
