# ONE-TIME-SALES-AND-MARKETING-LTD.
Python exploratory data analysis of 1,001 sales transactions: salesperson performance, data preprocessing, visualisation and statistical testing with pandas, seaborn and SciPy.
# Sales Performance Analysis in Python

Exploratory data analysis (EDA) of 1,001 sales transactions between June and November 2020. The project compares the performance of three salespeople (Kelly, Peter and Pryia) and tests whether order priority is related to sale value.

## Questions
1. How do total and average sale values differ between the three salespeople?
2. Is there a statistically significant relationship between order priority and sale value?

## Dataset
- **File:** `Sales Data PDA 4052.csv`
- **Rows:** 1,001
- **Columns:** `order_id`, `customer_id`, `sales_person`, `priority`, `ship_mode`, `date`, `value_£`
- **Period:** June to November 2020
- **Note:** the file needs `encoding='latin-1'` because of the £ symbol.

## Tools
Python 3, pandas, NumPy, Matplotlib, seaborn, SciPy (run in Google Colab).

## Workflow
1. **Import and inspection:** shape, data types, missing values, duplicates
2. **Type correction:** strip `£` and commas from `value_£` and convert to float, parse dates, cast categorical columns
3. **Descriptive statistics:** summary statistics, skewness, kurtosis, grouped totals
4. **Further preprocessing:** month features, ordinal encoding of priority (Low=0, Medium=1, High=2, Critical=3), IQR outlier flagging (outliers kept, not removed)
5. **Exploratory analysis:** eight visualisation groups (histograms, bar charts, boxplot, line chart, heatmap, scatter plot, stacked bar)
6. **Statistical testing:** Shapiro-Wilk, Spearman, Pearson, Kruskal-Wallis

## Key findings
- Pryia has the highest total sales (£672,229) and mean sale value (£1,989).
- Peter has the most transactions (344) but the lowest mean sale value (£1,597).
- Sale values are heavily right-skewed (skewness 3.77, kurtosis 17.42), so non-parametric tests were used.
- 122 transactions (12.2%) exceed the IQR upper fence of £4,340.73.
- Sale values differ significantly between salespeople (Kruskal-Wallis H = 6.027, p = 0.049).
- No significant correlation between priority and sale value (Spearman r = 0.063, p = 0.075; Pearson r = 0.037, p = 0.298).
- 21.3% of orders have priority "Not Specified" and were excluded from the priority analysis.

## Statistical tests
| Test | Result | Conclusion |
|---|---|---|
| Shapiro-Wilk | W = 0.497, p < 0.001 | Not normally distributed |
| Spearman | r = 0.063, p = 0.075 | No significant correlation |
| Pearson | r = 0.037, p = 0.298 | No significant correlation |
| Kruskal-Wallis | H = 6.027, p = 0.049 | Significant difference between salespeople |

## Limitations
- Only six months of data, so seasonality and long-term trends cannot be assessed.
- The "Not Specified" priority group may bias the priority analysis.
- No product, customer segment or margin data, so differences between salespeople cannot be fully explained.

## How to run
1. Open the notebook in Google Colab or Jupyter.
2. Upload `Sales Data PDA 4052.csv` to the same folder (adjust the filename in the import cell if needed).
3. Run all cells from top to bottom.

## References
- Field, A. (2018) *Discovering Statistics Using IBM SPSS Statistics.* 5th edn. London: SAGE Publications.
- Hair, J.F., Black, W.C., Babin, B.J. and Anderson, R.E. (2019) *Multivariate Data Analysis.* 8th edn. Andover: Cengage Learning.
- Kuhn, M. and Johnson, K. (2019) *Feature Engineering and Selection.* Boca Raton: CRC Press.
- McKinney, W. (2022) *Python for Data Analysis.* 3rd edn. Sebastopol: O'Reilly Media.
- Osborne, J.W. (2013) *Best Practices in Data Cleaning.* London: SAGE Publications.
- Tukey, J.W. (1977) *Exploratory Data Analysis.* Reading, MA: Addison-Wesley.
