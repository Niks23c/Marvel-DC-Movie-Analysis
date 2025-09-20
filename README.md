# Marvel vs DC Movie Analysis 🎬⚡  

## 📌 Project Overview  
This project is an **end-to-end data analysis pipeline** comparing the Marvel Cinematic Universe (MCU) and DC Extended Universe (DCEU) movies.  

It demonstrates skills in:  
- **Web Scraping** (Requests)  
- **Data Cleaning & Transformation** (Pandas)  
- **Dashboard Building** in Power BI  

The goal is to uncover insights on **box office trends, budgets, ratings, and awards** between MCU and DC movies.  

---

## ⚙️ Tools & Technologies  
- **Python:** Requests, Pandas, merge, concat 
- **SQL:** SQLite (portable, beginner-friendly)  
- **Power BI:** Data modeling & visualization  
- **Colab / Jupyter:** Code development & experimentation  
- **GitHub:** Version control & documentation  

---

## 🕸️ Step 1: Web Scraping  
We scraped **movie tables** from Wikipedia pages of MCU and DCU.  

- **Source Pages:**  
  - [Marvel Cinematic Universe films](https://en.wikipedia.org/wiki/Marvel_Cinematic_Universe)  
  - [DC Extended Universe films](https://en.wikipedia.org/wiki/DC_Extended_Universe)
  - [DC Universe franchise](https://en.wikipedia.org/wiki/DC_Universe_(franchise) # took new stage film also "Superman 2025" as to compete with fantastic fours

- **Process:**  
  1. Used `requests` to fetch HTML.  
  2. Parsed HTML with pandas.  
  3. Extracted the movie tables into Pandas DataFrames.  
  4. Standardized the columns across both universes.  

- **Initial Issues Faced:**  
  - Some rows contained headers like *“Phase Two”* or *“Phase Three”* → Dropped during cleaning.  
  - Column orders between MCU and DCU didn’t match (Budget/Box Office swapped) → Fixed by reordering columns.  
  - Box office and budget values contained currency symbols and ranges → Cleaned using regex and converted to numeric.  
  - Rotten Tomatoes column contained percentage strings → Converted to integers.  

✅ **Outputs:**  
- `mcu_clean.csv`  
- `dcu_clean.csv`  

---

## 🧹 Step 2: Data Cleaning & Transformation  
Performed in **Google Colab** with Pandas.  

- Merged MCU and DCU into one table (`movies_clean`).  
- Standardized numeric fields (`Budget`, `Box Office`).  
- Removed unnecessary rows (phase headers).  
- Ensured consistent date formats in `Release_Date`.  

👉 At this stage, had a **unified dataset of both universes**, ready for analysis.  


---

## 📊 Step 3: Power BI Dashboard  
Final step will be to create an **interactive dashboard**:  
- KPIs:  sum of Box Office, Avg Ratings (MCU vs DC), Awards Won
- Trends: Release timelines with box office success vs Budget
- Trends: release time line with awrds won vs Nominated
- Comparison: Top 5 grossing movies in each franchise  
- Awards impact on revenue  co-relation

- screenshots will be stored in the `powerbi/` folder.  

---

## ⚠️ Challenges Encountered  
- Wikipedia tables had inconsistent formatting across MCU & DC.  
- Box office and budget values were in **mixed formats** (commas, ranges, “million” text).  
- Rotten Tomatoes column contained **string values** like “87%” → needed regex conversion.  
- Joining ratings/awards datasets initially created **NaN values** because of name mismatches (extra spaces, different titles).  

---

## 📂 Repository Structure  
