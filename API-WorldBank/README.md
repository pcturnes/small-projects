# 🏦 World Bank API Analysis: Global Indicators (LAB 1)

This repository contains the solution for **LAB 1: APIs - WORLD BANK** for the **Master in Big Data Analytics** program, focusing on the retrieval, filtering, and analysis of global economic and demographic indicators using the World Bank API.

## 👥 Authors

* **Yihang Zhu**
* **Pablo Cano Turnes**
* **Aleksandr Veretelnik**
* **Miguel Rodríguez Losada**

---

## 🎯 Lab Goal

The primary objective is to gain practical experience using a widely-used, real-world API—the **World Bank API**—to access and process large datasets on countries' economic, health, and social indicators. The lab emphasizes data curation, filtering out non-country aggregates, and performing comparative analysis across different time periods and income groups.

* **Indicator Used:** Data from the World Bank's development indicators API.
* **Implementation:** The solution is implemented in a **Jupyter Notebook** (or equivalent script) using Python.

---

## 🛠️ Setup and Documentation

Before running the lab, students must be familiar with the World Bank API structure.

### 📚 Key Documentation Links

* **API Basic Call Structures:** [https://datahelpdesk.worldbank.org/knowledgebase/articles/898581-api-basic-call-structures](https://datahelpdesk.worldbank.org/knowledgebase/articles/898581-api-basic-call-structures)
* **Developer Information:** [https://datahelpdesk.worldbank.org/knowledgebase/topics/125589-developer-information](https://datahelpdesk.worldbank.org/knowledgebase/topics/125589-developer-information)
* **Indicators API:** [https://datahelpdesk.worldbank.org/knowledgebase/articles/889392-about-the-indicators-api-documentation](https://datahelpdesk.worldbank.org/knowledgebase/articles/889392-about-the-indicators-api-documentation)
* **Indicator Search Tool:** [https://data.worldbank.org/indicator?tab=featured](https://data.worldbank.org/indicator?tab=featured)

### 💻 Libraries Used

The solution relies on the following Python libraries for data retrieval and manipulation:

* **`requests`**: For making HTTP requests to the World Bank API.
* **`pandas`**: For data processing, cleaning, merging, and analysis, particularly using `pd.json_normalize` for parsing the nested JSON structure.

---

## ✨ Milestones

The lab is structured around **5 milestones**, each requiring the use of a specific indicator and data manipulation techniques. **Crucially, all analyses exclude regions and aggregate entities.**

### 1️⃣ MILESTONE 1: Population (`SP.POP.TOTL`)

* **Task:** Retrieve the **2022** total population for all valid countries.
* **Output:** Display the **Top 10** and **Bottom 10** countries by population.
* **Key Technique:** Filtering API results using country metadata to exclude World Bank Aggregates (e.g., "World", "High income").

### 2️⃣ MILESTONE 2: Women vs. Men Population (`SP.POP.TOTL.FE.ZS`, `SP.POP.TOTL.MA.ZS`)

* **Task:** Obtain the **2022** percentage of men and women for each country and compute the difference: `%women - %men`.
* **Output:**
    * Count of countries with **more women** than men.
    * Count of countries with **more men** than women.
    * The **Top 10** countries with the largest positive difference (more women).
    * The **Top 10** countries with the largest negative difference (more men).

### 3️⃣ MILESTONE 3: GDP Per Capita Increase by Income Group (`NY.GDP.PCAP.CD`)

* **Task:** Compute the **average percentage increase/decrease** in GDP per capita (in US dollars) for five specific **World Bank Income Groups** (Low, Lower-Middle, Middle, Upper-Middle, High Income).
* **Periods:** $2000-2022$ and $2010-2022$.
* **Formula:** $$\% \text{ increase} = 100 \times \frac{(\text{GDP}_{final} - \text{GDP}_{initial})}{\text{GDP}_{initial}}$$

### 4️⃣ MILESTONE 4: Top 5 Countries’ GDP Increase Per Income Group

* **Task:** Using the data from Milestone 3, list the **Top 5 countries** within *each* of the five income groups based on the highest **% GDP per capita increase** for the period **$2010-2022$**.

### 5️⃣ MILESTONE 5: $\text{CO}_2$ Emission Per Capita (`EN.GHG.ALL.PC.CE.AR5`)

* **Task:** Retrieve the **Most Recent Non-Empty Value (MRNEV)** for Total greenhouse gas emissions (excluding LULUCF) per capita ($\text{t} \text{CO}_2 \text{e}/\text{capita}$) for all countries.
* **Output:** Display the **Top 30 countries** with the highest emissions per capita, including the **value** and the **year** of the observation.
* **Key Technique:** Utilizing the `MRNEV=1` parameter in the API call to automatically retrieve the latest available data point, rather than specifying a fixed date.

---

## 🛑 Important Notes

* **Data Validation:** The solution includes a necessary initial step to fetch country metadata and create a filter (`get_valid_country`) to ensure that all subsequent API calls exclude aggregated non-country entries.
* **Efficiency:** The requests utilize a high `per_page` value (`20000`) to minimize the number of API calls, adhering to a principle of **maximum efficiency** in data retrieval.
* **Submission:** The complete solution notebook/script must be uploaded to Aula Global. The final grade is based on the successful completion of these milestones, which will be verified by the professor.