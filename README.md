# 🌾 Global Agricultural Production : Exploratory Data Analysis

An exploratory data analysis (EDA) project on **global crop and livestock production**, using real-world data from **FAOSTAT** (the Food and Agriculture Organization's statistical database). The project cleans a messy real-world dataset and walks through 7 structured analyses to uncover patterns in what the world produces, who produces it, and how that's changed over six decades.

## 📊 About the Dataset

⚪ **Source:** FAOSTAT : Production: Crops and Livestock (Normalized)

⚪ **Coverage:** 1961–2024, across countries/regions and hundreds of agricultural items

⚪ **Key columns used:** `Area`, `Area Code (M49)`, `Item`, `Element`, `Year`, `Unit`, `Value`

### 🧹 Data Cleaning
Real-world statistical datasets are rarely analysis-ready, and this one was no exception:

⚪ Removed rows with missing `Value` entries

⚪ Filtered out **aggregate/category rows** (e.g. "Cereals, primary", "Meat, Total") to avoid double-counting individual crops within their own totals

⚪ Cleaned the `Area` column, which unexpectedly contained non-country entries like **"World"** and even **"Paris"** , filtered down to valid countries using official **UN M49 area codes**, so country-level analysis reflects actual countries only

## 🛠️ Tools & Libraries

⚪ **pandas** ➔ data cleaning, grouping, aggregation, merging

⚪ **matplotlib** ➔ all visualizations (bar charts, line charts, scatter plots)

## 🔍 The 7 Analyses

### 1️⃣ Top 10 Agricultural Products by Total Production
Identifies which products have the highest total recorded production worldwide.
> **Finding:** Sugar cane leads by a wide margin, followed by hen eggs in shell, maize, rice, and wheat.
>
> Analysis graph :
>
>
>  <img width="790" height="484" alt="1 1" src="https://github.com/user-attachments/assets/d93ab55e-24fe-49cc-9a3e-6ee9ac0616de" />


### 2️⃣ Global Agricultural Production Trend Over Time
**2.1 ** Tracks total global production from 1961 to 2024.
> **Finding:** A strong, steady upward trend for decades production peaked in 2023, then dropped ~6.4% in 2024.
>
> Analysis graph :
>
> <img width="794" height="503" alt="2 1" src="https://github.com/user-attachments/assets/0ab88ea1-3a41-4f40-8e4e-88d7b3d7bb22" />


**2.2 ** Investigates *why* 2024 dropped. Rather than assuming a real production decline, this digs into whether it's a **data coverage issue** comparing the number of records and represented products between 2023 and 2024.
> **Finding:** Both the number of production records and the number of represented products drop noticeably in 2024, suggesting the decline is likely driven by **incomplete reporting** for that year (countries/products not yet fully reported) rather than a confirmed real-world downturn though external factors like weather or funding disruptions can't be ruled out either.


Analysis graph :

<img width="798" height="393" alt="2 2" src="https://github.com/user-attachments/assets/428499a2-fd6b-49e4-80b8-9560d9077aaf" />



### 3️⃣ Contribution of the Top 10 Products to Total Production
Calculates what share of total global production comes from just the top 10 products.
> **Finding:** The top 10 products account for ~59.5% of total recorded production sugar cane, hen eggs, maize, rice, and wheat lead the share.
>
> Analysis graph :
>
> <img width="782" height="480" alt="1 3" src="https://github.com/user-attachments/assets/10c5781e-469b-4aac-a1e9-67e2fd066ebd" />


### 4️⃣ Top Countries by Highest Production
Identifies which countries contribute the most to global agricultural output.
> **Finding:** Argentina records the highest total production, followed by Australia and Bangladesh.
>
> Analysis graph :
>
> <img width="790" height="483" alt="1 4" src="https://github.com/user-attachments/assets/3ac39aee-083b-4f21-83bf-80caae3c005c" />


### 5️⃣ Production Increment Over Time (1961–2023)
Compares 1961 vs. 2023 figures to find which products grew the most in absolute terms.
> **Finding:** Maize shows the largest absolute increase, followed by rice, wheat, and raw cattle milk.
>
> Analysis graph :
>
> <img width="790" height="461" alt="1 5" src="https://github.com/user-attachments/assets/1c3d8a2f-b62b-4f12-906b-0d379de251b0" />


### 6️⃣ Production vs. Yield Relationship
Tests whether higher yield (output per hectare) correlates with higher total production, using 2023 data.
> **Finding:** A very weak positive correlation (~0.029, calculated at the country level)  meaning higher yield efficiency doesn't strongly predict higher total production. Total output is likely driven more by **land area under cultivation** than by yield efficiency alone.
>
> Analysis graph :
>
> <img width="786" height="477" alt="1 6" src="https://github.com/user-attachments/assets/5f52ec82-0bfb-4d21-8ce9-3231c46846eb" />


### 7️⃣ Data Coverage Overview
A closing look at how consistently data has been reported across recent years (2019–2024).
> **Finding:** Record counts stayed fairly stable from 2015–2023, with a clear drop-off in 2024 reinforcing the reporting-gap explanation from Analysis 2.2.
>
> Analysis graph :
>
> <img width="786" height="397" alt="1 7" src="https://github.com/user-attachments/assets/c2310621-35bb-42ee-ad1f-180ab1a48c02" />


## 💡 Key Takeaways

⚪ A handful of staple crops (sugar cane, cereals, maize, rice, wheat) dominate global production

⚪ Global production has grown consistently since 1961, with the 2024 dip likely explained by **data reporting lag**, not a real collapse in output

⚪ Yield efficiency and total production are only weakly related  scale of production matters more than efficiency per hectare

⚪ Real-world datasets need careful cleaning  this dataset alone required filtering out non-country entries and aggregate rows to get accurate results

## 🔮 Future Improvements

⚪ Add per-capita production analysis (adjusting for population) for fairer country comparisons

⚪ Investigate 2024 reporting gaps further by cross-referencing FAOSTAT's own metadata/notes

⚪ Build an interactive dashboard (Plotly/Streamlit) instead of static plots

⚪ Extend yield analysis to specific crop categories rather than production as a whole

## 🤝 Contributing

Suggestions and feedback are welcome! Feel free to open an issue or fork the repo.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
