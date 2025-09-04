# Understanding Inflation in Canada: Affordability, Financial Strain, and Economic Stability

*A Decision Intelligence Analysis of Inflation in Canada*

*Author: Adaobi Obua*

## Executive Summary
This study analyzes inflation trends in Canada through the lens of Consumer Price Index (CPI) growth, wage growth reports, housing affordability, and monetary policies. Using comprehensive datasets from Statistics Canada, the Bank of Canada, and CMHC, we examine how inflation affects affordability in different economic sectors and whether current monetary policies are effective in maintaining price stability. By analyzing these datasets, this research aims to provide insights into the long-term economic implications of inflation in Canada and offer data-driven recommendations for policymakers, businesses, and individuals.

[Read detailed background information here](Background.md)

[See Supplemental information here](Supplemental.md)

## Key Performance Indicators (KPIs)

### Consumer Price Index (CPI) Growth Rate

The Consumer Price Index (CPI) is a vital Key Performance Indicator (KPI) for understanding inflation trends and their impact on economic stability in Canada.


Summary details:

- Measures the percentage change in the Consumer Price Index (CPI) over a specified period (monthly or yearly).   
- CPI is the primary indicator of inflation, showing how the average price level of a basket of goods and services changes over time.

### Core Inflation Rate
- Inflation rate that excludes volatile items such as food and energy prices.
- Provides a more stable view of inflation trends by removing short-term price fluctuations.

### Purchasing Power of the Canadian Dollar
 - Measures how much the value of the Canadian dollar has changed over time in terms of its ability to purchase goods and services.
- Helps assess the real impact of inflation on consumers and businesses.

### Wage Growth vs. Inflation Rate
- Compares the growth in average wages to the inflation rate to determine if wages are keeping up with rising costs.
- If wages grow slower than inflation, consumers lose purchasing power, leading to reduced economic well-being.

![CPI](CPI/All.png)
- This graph details the average CPI determined from all goods from 1992 to 2025.
  
![CPI](Inflation/fi2.png)
- This chart details all product categories used to determine annual average CPI.
  
![FOOD](Food/Products.png)
-  This graph details the monthly average price of selected food items from 2017 to 2024.
  
![WAGE](Wage/All.png)
- This graph details the average wage for all industries from 1997 to 2024.

![Inflation](Inflation/fi1.png)
- This graph shows change in inflation measures Total CPI, CPI-trim, CPI-Common, and CPI-Median from 1992-2025.


# Exploratory Data Analysis
![CPI](CPI/fi3.png)

Key Insights from Correlation Matrix Heat Map

Year strongly correlates with Wage (0.99) and Average_CPI (0.98): This suggests that over time, wages and average CPI have increased consistently, implying a likely causal relationship from Year to Wage and Average_CPI.
Total_CPI also strongly correlates with Average_CPI (0.99): This very high correlation indicates that Total_CPI is likely a strong driver or direct contributor to Average_CPI.
Cpi_Common, Cpi_Median, Cpi_Trim correlate well with Total_CPI (ranging from 0.85 to 0.98): These are likely components or inputs to Total_CPI.

Inferred Causal Relationships
- Year → Wage: Economic growth and cost-of-living adjustments drive wage increases.
- Year → Average_CPI: Inflation grows over time.
- Total_CPI → Average_CPI: Total CPI directly influences or composes Average CPI.
- Cpi_Common, Cpi_Median, Cpi_Trim → Total_CPI: These are likely individual CPI components contributing to the total.

Discussion

Wage increases are highly time-dependent, likely reflecting economic growth and cost-of-living adjustments. Average_CPI is most influenced by Total_CPI, which itself is a function of Cpi_Common, Cpi_Median, and Cpi_Trim. Year serves as a confounding driver across all economic indicators, acting more like a proxy for economic progress.

# Statistical Analysis
The inferred relationship between the variables derived from the correlation matrix were used to interpret a causal relationship through causal inference.


![CPI](CPI/fi4.png)
- Relationship between Year and Average CPI
  
![CPI](CPI/fi5.png)
- Relationship between Wage and Average CPI
  
![CPI](CPI/fi6.png)
- Directed graph (digraph) theoretical model
  
![CPI](CPI/fi7.png)

- Data-derived model

![CPI](CPI/fi8.png)

- Refined casual digraph model

Discussion

The causal effect was identified to understand how the variables in the causal model are related. To estimate the magnitude of the effect, the instrument variable method was used as the backdoor linear regression and other models did not work. Using “Year” as the instrument in this analysis, the mean value of the casual estimate is 3.458. This value tells us how much change in “Total CPI” is expected to impact “Average CPI” and suggests that, on average one unit of increase in “Total CPI” is associated with an increase in “Average CPI” of approximately 3.458 units. 

Refute Analysis

The refutation step was done with a placebo treatment refuter as the random common cause method did not work with our instrument variable. However, the new effect estimate is 107.9 and the p value is 0.99. This implies that the casual effect or method used to calculate the estimate is not robust as it changed significantly when applied. This raises questions about the validity of the initial estimate and may point to the fact that a wrong estimation method was used. I am unable to validate the causal effect otherwise as other estimation methods did not work for my dataset. 

# Conclusion

The data reveals strong interdependencies between time, wage levels, and inflation indicators. The correlation causal model indicates that while time drives most economic changes, the breakdown of CPI components also plays a crucial role in shaping the overall inflation picture. However, the causal inference model shows that the estimated effect is not robust due to the significant difference and high p-value from the refutation step. This indicates that causal inference is not the best method to determine causality, rather than an issue with correlation in the data itself.

