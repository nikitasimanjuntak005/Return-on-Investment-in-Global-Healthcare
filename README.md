# DV-2526ge-02

## Return on Investment in Global Healthcare

A Tableau Data Story on Healthcare Spending, Life Expectancy, and Efficiency.

## Project Description

This project explores the relationship between healthcare spending and life expectancy across countries worldwide using Tableau visualizations. The main purpose of this project is to investigate whether massive healthcare spending always leads to better health outcomes and longer life expectancy.

The project focuses on the phenomenon of diminishing returns in global healthcare systems, where increasing healthcare expenditure no longer produces proportional improvements in human life expectancy. Through a data storytelling approach, this project highlights how some countries achieve high life expectancy with relatively moderate healthcare spending, while others spend significantly more without obtaining comparable healthcare outcomes.

A major focus of this analysis is the anomaly of the United States, which has the highest healthcare spending per capita in the world but does not achieve the highest life expectancy compared to countries such as Japan, Singapore, and Switzerland.

This project answers several important analytical questions:
- Does higher healthcare spending always guarantee longer life expectancy?
- Which countries achieve the most efficient healthcare ROI?
- Why do some countries experience diminishing returns despite massive healthcare investment?
- How do healthcare infrastructure and mortality rates relate to healthcare efficiency?

The visualizations provide insights into healthcare efficiency, healthcare infrastructure, mortality trends, and global healthcare investment outcomes.

## Data Source

The data for this project is sourced from a public Kaggle dataset:

**Healthcare ROI Profiling Dataset**  
https://www.kaggle.com/datasets/belbino/life-expectancy-healthcare-spending-1960-present

## CSV Files Used
- `health_panel.csv`
- `health_spending.csv`
- `hospital_capacity.csv`
- `infant_mortality.csv`
- `life_expectancy.csv`
- `ml_features.csv`
- `context.csv`
- `country_metadata.csv`

## Data Description

The dataset contains global healthcare and economic indicators from multiple countries worldwide between **1960–2023**. However, this project only focuses on the **2010–2019** period because the data in this range is more complete, more consistent, and better represents modern healthcare systems before the COVID-19 pandemic.  

The data includes:
- Healthcare spending per capita
- Life expectancy
- Healthcare infrastructure capacity
- Physicians and hospital beds
- Infant and maternal mortality
- Economic and demographic indicators
- Healthcare efficiency metrics

## Data Cleaning and Transformation

The data was cleaned and transformed using **Python (pandas & NumPy)** before being visualized in Tableau. The preprocessing workflow included:
- Merging multiple datasets using `country_code` and `year`
- Removing redundant and empty columns
- Handling missing values using linear interpolation
- Applying median imputation for remaining missing numeric values
- Standardizing categorical values
- Filtering the dataset for the 2010–2019 period

The final cleaned dataset was exported into CSV format and used as the primary data source for Tableau visualization.  


## Tableau Visualizations
**1. Healthcare Spending vs Life Expectancy (Global Overview)**
### Purpose: 
This visualization aims to examine the relationship between healthcare spending per capita and average life expectancy across countries worldwide. The scatter plot serves as the background analysis for the project by testing the widely held assumption that higher healthcare spending necessarily leads to longer life expectancy.
More specifically, the visualization helps identify the phenomenon of diminishing returns in healthcare investment, where increasing financial resources allocated to healthcare systems no longer produce proportional improvements in population health outcomes.
### Key Features:
**Chart Type** 
* A scatter plot representing the relationship between two quantitative variables:
   * X-axis: Average Healthcare Spending per Capita (USD)
   * Y-axis: Average Life Expectancy

**Data Points**: Each point represents one country from the dataset contained in cleaned_health_data.csv.

**Distribution Pattern**: The plot displays the global distribution of countries based on healthcare investment and health outcomes, allowing users to visually observe patterns and clusters among low-, middle-, and high-spending countries.

**Comparative Positioning**: Countries with extremely high healthcare spending (e.g., the United States) can be compared with countries that achieve similar or better life expectancy with lower spending, such as Japan or Singapore.

**Interactive Elements**: Hovering over individual points reveals tooltips containing detailed information such as:
   * Country name
   * Average healthcare spending per capita
   * Average life expectancy

### Insights:
Several important insights can be derived from this visualization:
* **Positive Relationship at Early Spending Levels**

At low to moderate levels of healthcare spending, there is a noticeable positive relationship between healthcare expenditure and life expectancy. Countries that increase healthcare investment often experience substantial improvements in health outcomes. This finding aligns with health economics research showing that early investments in healthcare infrastructure and services produce high marginal health gains.
* **Evidence of Diminishing Returns**

After healthcare spending reaches approximately $3,000–$4,000 per capita, the relationship begins to flatten. Countries that spend significantly more tend to cluster within a narrow life expectancy range of roughly 80–84 years. This plateau indicates a diminishing return effect, where additional financial investment yields progressively smaller improvements in life expectancy.
* **The United States as a Notable Outlier**

One of the most prominent patterns in the scatter plot is the presence of countries with extremely high healthcare spending but relatively moderate life expectancy. The United States is frequently cited in global health research as an example of this phenomenon. Despite having the highest healthcare expenditure per capita globally, the United States does not achieve the highest life expectancy compared to other developed nations.
* **Evidence of Healthcare System Efficiency**

Several countries achieve high life expectancy with significantly lower healthcare spending. Countries such as Japan, Singapore, and Switzerland demonstrate that efficient healthcare systems can produce superior health outcomes without excessive spending. This observation highlights the importance of system efficiency, preventive care, and effective resource allocation, rather than simply increasing healthcare budgets.

**2. Healthcare Infrastructure Comparison**
### Purpose:
The purpose of this visualization is to investigate whether countries with higher healthcare spending actually maintain greater healthcare infrastructure capacity. By comparing these structural indicators, the visualization helps explore whether large healthcare expenditures translate into stronger medical infrastructure or whether inefficiencies exist within certain healthcare systems. This analysis also provides deeper context for the anomaly observed in the previous visualization, where some countries spend significantly more on healthcare without achieving proportionally better health outcomes.

### Key Features:
**Chart Type**

The visualization uses a dual bar chart layout (stacked vertically) to present two infrastructure indicators:
* Physicians per 1,000 population
* Hospital beds per 1,000 population
This layout allows users to compare workforce capacity and facility capacity simultaneously across countries.

**Country Comparison**

The visualization includes four countries commonly referenced in global healthcare system comparisons:
* Japan
* Singapore
* Switzerland
* United States
These countries represent different healthcare system models and spending levels, making them suitable for examining differences in healthcare efficiency.

**Comparative Visualization Design**

By presenting both indicators together, users can observe whether countries that spend more on healthcare also maintain higher levels of:
* medical workforce availability
* healthcare facility capacity
This structure helps reveal potential mismatches between healthcare spending and infrastructure investment.

### Insights:
* High healthcare spending does not necessarily translate into larger infrastructure
* Japan demonstrates strong healthcare infrastructure
* Balanced healthcare systems in Singapore and Switzerland
* Evidence of structural inefficiencies
* Rather than expanding healthcare infrastructure, these cost drivers may reduce overall system efficiency.

**3. Maternal Mortality per 100k (2010-2019)**
### Purpose:
This visualization aims to show the real impact of cost in human lives in an inefficient healthcare system. It highlights how a wasteful system fails to protect vulnerable populations (expectant mothers) by comparing the historical trends of the US against highly efficient nations.

### Key Features:
* A line chart tracking historical trends over a decade (from 2010 to 2019) along the X-axis.
* The Y-axis displays the maternal mortality ratio per 100,000 live births.
* Direct text labels placed at the end of the chart (United States, Japan, Singapore, Switzerland) for immediate identification, eliminating the need for a separate color legend.

### Insights:
* Unequal Protection of Vulnerable Groups: A stark contrast is evident. Highly efficient countries like Japan, Singapore, and Switzerland have successfully maintained their maternal mortality rates at the absolute lower bound, nearly touching zero.
* The United States' Regression: This is the bitter reality of the data story. Despite spending the most money globally, the maternal mortality rate in the US is not only significantly higher than in other developed nations, but the trend is actually climbing upward from 2010 to 2019. This proves that giant budgets do not guarantee adequate basic care or better health outcomes.

**4. Healthcare ROI: Life Expectancy Yield per $1,000 Spent**
### Purpose:
This visualization aims to straightforwardly rank the efficiency of countries worldwide. It precisely measures which nations are the most successful and the most unsuccessful at converting every $1,000 spent into additional life expectancy for their citizens.

### Key Features:
* A bar chart that ranks countries based on their efficiency levels.
* Utilizes a specific calculated field on its axis, namely the le_per_1k_spend column, which is formulated as: (Life Expectancy / Total Healthcare Spending per Capita) x 1000.
* Sorted to place countries with the highest ROI at the very top and those with the lowest ROI at the very bottom.

### Insights:
* Global Efficiency Champions: The length of the bars clearly reveals the true winners. Asian countries like Singapore, Japan, and South Korea dominate the top positions, proving their healthcare models are the most effective at turning funds into longevity.
* The Giant's Failure (United States): The United States is stranded at the very bottom of the chart. This serves as the final proof solving the project's core mystery: the most gigantic budget does not correlate at all with the life expectancy gained. The US wastes too much money with a remarkably low return on investment (ROI) in human lives.

## How to Use the Visualizations

* **Navigate Between Views**: Use the tabs (or story points) at the top of the Tableau workbook to navigate sequentially through the four main chapters of the data story. Start from the "Triliunan Dolar yang Gagal Membeli Umur" scatter plot to understand the background, move through the infrastructure and mortality charts to analyze the inefficiencies, and conclude at the "Pahlawan Efisiensi: Model Rujukan Dunia" bar chart for the final resolution.
<img width="1920" height="1080" alt="navigation" src="https://github.com/user-attachments/assets/e09d95ac-9068-4634-8331-dedef1941f46" />

* **Interact with Legends and Highlighting**: Click on specific countries (such as the United States, Japan, Singapore, or Switzerland) directly within the charts or via the color legends to highlight their specific data marks. This action will dim the other data points, allowing you to easily isolate and compare the performance of these key nations across different metrics.
<img width="1920" height="1080" alt="highlight" src="https://github.com/user-attachments/assets/e7790944-8ddb-412e-82af-703478c87675" />

* **Utilize Tooltips for Deep Dives**: Hover your cursor over any data point, line, or bar across all four visualizations to reveal a tooltip with specific, detailed information:
    * In the Scatter Plot, hovering over a dot reveals the Country Name, exact Healthcare Spending per Capita (USD), and Life Expectancy.
    * In the Infrastructure Bar Chart, hovering over the bars displays the exact number of hospital beds or medical staff per 1,000 people.
    * In the Maternal Mortality Area Chart, hovering along the timeline shows the exact mortality rate per 100,000 live births for a specific country in a given year.
    * In the ROI Bar Chart, hovering over a bar reveals the exact le_per_1k_spend score, showing precisely how much life expectancy is gained per $1,000 spent.
<img width="1920" height="1080" alt="tooltip" src="https://github.com/user-attachments/assets/f0cb67d3-629b-4e5f-8496-b527a8688665" />

* **Analyze Static Annotations**: Pay close attention to the built-in text annotations and trend lines (particularly in the scatter plot and area chart). These are designed to instantly guide your eye to the core narrative: the stark contrast between the massive spending of the United States and the high efficiency of countries like Japan, Singapore, and Switzerland.

## Tableau Workbook

The Tableau workbook (`.twbx`) file is located in this repository: /apps/Final.twb
---
https://public.tableau.com/shared/DM756TNTS?:display_count=n&:origin=viz_share_link 

## Contributions

- 12S22005 - Nikita Simanjuntak (@nikitasimanjuntak005)
- 12S22009 - Dolok O.P. Butarbutar (@dolokbutarbutar24)
- 12S22014 - Kezia Judika Manira Hutagaol (@keziahutagaol)
- 12S22021 - Krisnia Calysta Siahaan (@krisniasiahaaan)
- 12S22034 - Mulyadi Yamin Siahaan (@mulyadiyaminsiahaan)
- 12S22038 - Ade Yohana Azeka Siahaan (@adshnn)

Contributions are welcome! If you have suggestions for improvements or find any issues, please:

* Fork this repository.
* Create a new branch with your changes.
* Submit a pull request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

*Note: This project was created for academic and educational purposes as part of the 12S4052 - Data Visualization course at Institut Teknologi Del.*

## Acknowledgments

Special thanks to:
- Kaggle for providing the Life Expectancy / Healthcare Spending 1960-Present Dataset
- Tableau for the data visualization platform
- Lecturers and teaching assistants of the Data Visualization course for their guidance and feedback
