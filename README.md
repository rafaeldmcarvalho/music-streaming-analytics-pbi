# Spotify User Behavior Analysis & Dashboard

## 📌 Project Overview
This project provides a comprehensive analysis of user engagement, subscription trends, and feature preferences for a music streaming platform. Using a dataset of 50,000 synthetic user records, I developed an interactive Power BI dashboard to help stakeholders identify churn risks and optimization opportunities.

## 🎯 Key Business Questions
- **Conversion Efficiency:** What is the specific user profile (Age/Country/Device/Most Liked Feature) that converts most effectively from ads to subscriptions?
- 
- 
- 

## 📂 Project Structure
- `data/`: Contains the raw CSV dataset.
- `notebooks/`: Jupyter Notebooks with the Python ETL process.
- `pbix/`: Power BI project files.
- `assets/`: Documentation, icons, and images.
- `README.md`: Project documentation.

## 🛠️ Tool Stack
- **Data Processing:** Python (Pandas) inside Jupyter Notebooks
- **Environment Management:** Conda
- **Data Visualization:** Power BI Desktop
- **Calculations:** DAX (Data Analysis Expressions)
- **Documentation:** Markdown / GitHub

## ⚙️ ETL Process (Python)
Before importing to Power BI, the data underwent a cleaning process to ensure analytical quality:
- **Date Standardization:** Converted strings to `datetime` objects for time-series consistency.
- **Boolean Mapping:** Transformed "Yes/No" columns into `1/0` for mathematical efficiency in DAX measures.
- **Feature Engineering:** Calculated user **Tenure** and created **Age Groups** for granular demographic analysis.
- **Data Quality:** Handled outliers in listening habits and verified reference dates (2025-12-31).

## 📐 Data Modeling (Star Schema)
To optimize performance, the flat dataset was restructured into a **Star Schema**:
- **Fact Table:** `spotify_cleaned` containing metrics like listening hours, skips, and status flags.
- **Dimension Tables:** Created specific dimensions for `dim_country`, `dim_subscription`, `dim_genre`, and `dim_device`.
- **Relationships:** Established 1:N (one-to-many) relationships using Surrogate Keys to ensure data integrity.

## 📅 Time Intelligence (dCalendar)
To enable advanced temporal analysis, a dedicated **dCalendar** table was implemented using DAX.
- **Dynamic Range:** Spans from the earliest signup to the reference date.
- **Attributes:** Includes Year, Month Name, Quarter, and Year-Month strings.
- **Key Feature:** Allows for Time Intelligence calculations such as Year-over-Year growth and Monthly Trends.

### 📈 Conversion Insights Dashboard
The dashboard focuses on identifying the **Ideal Customer Profile (ICP)** through:
- **Geographic Performance:** Mapping conversion rates across different countries.
- **Value Proposition:** Analyzing how different app features (Most Liked Features) drive users to subscribe.
- **Age Demographics:** Analyzing the impact of user age on ad-to-premium conversion.
- **Device Affinity:** Analyzing conversion rates across Smartphone, Desktop, Smart Speakers, and Tablets to identify platform-specific friction points.

## 💡 Main Findings & Business Insights
- **Target Audience:** The **35-44 age group** shows the highest conversion peak (~26%), suggesting that premium ads are highly effective with a mature, established audience.
- **Conversion Drivers:** Personalization features (AI DJ and Discover Weekly) are the strongest hooks for upgrading, outperforming utility features like "Offline Mode" in conversion probability.
- **Market Leaders:** Emerging markets like **Indonesia** and **Mexico** present higher ad-receptivity, offering a strategic opportunity for aggressive growth campaigns.
- **Platform Consistency:** **Mobile** leads in volume, but the conversion gap between Mobile and **Desktop/Tablet** is minimal (~1%), indicating a high-quality cross-platform user experience.


---

## 🚀 How to View the Project
1. Clone the repository.
2. Open the `.pbix` file in **Power BI Desktop**.
3. *[Optional]* Check the `/notebooks` folder to see the data transformation logic.

---

## ⚙️ Environment Setup
To replicate the Python environment, use Conda:
```bash
conda create --name spotify-env python=3.12 pandas ipykernel
conda activate spotify-env
