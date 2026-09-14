# Fashion Retail Sales Analysis

## 📌 Overview
This project analyzes fashion retail transaction data to understand what drives purchase volume, spending, and customer satisfaction — with the goal of identifying insights a retailer could act on around pricing, product mix, and payment trends.

## ❓ Question(s) I set out to answer
- Which items are purchased most often, and which command the highest average spend?
- Does how much a customer spends relate to how they rate their purchase?
- Does payment method (Cash vs Credit Card) relate to spending or satisfaction?
- Are there seasonal patterns in purchase volume or spend across the year?

## 📊 Data
- **Source**: [Fashion Retail Sales dataset, Kaggle](https://www.kaggle.com/datasets/fekihmea/fashion-retail-sales)
- **Size**: 3,400 transactions, 6 columns
- **Columns**: Customer Reference ID, Item Purchased, Purchase Amount (USD), Date Purchase, Review Rating, Payment Method
- **Format**: CSV

## 🛠️ Tools used
- Excel (PivotTables, CORREL function, charts)

## 🧹 Data cleaning
- Identified missing values in the Review Rating column — a number of transactions have no rating recorded. These were left blank rather than deleted, since the purchase itself is still valid data; Excel's AVERAGE and CORREL functions were confirmed to correctly ignore blanks rather than treating them as zero.
- Verified Date Purchase was read as an actual date type (not text) to allow grouping by month.

## 🔍 Approach
1. Built a PivotTable grouping transactions by Item Purchased, calculating both purchase count and average purchase amount per item.
2. Used the CORREL function and a scatter plot to test the relationship between Purchase Amount and Review Rating.
3. Built a PivotTable comparing average spend, transaction volume, and average rating across Cash vs Credit Card payments.
4. Built a PivotTable grouping transactions by month to check for seasonal spending patterns. *(in progress)*

## 📈 Key findings
- **Purchase volume is evenly spread, but spend is not.** Across ~50 item types, purchase counts ranged narrowly from 57–90 — no single item dominates sales volume. Average spend per item, however, varied widely: from $93 (Sunglasses) to $320 (Tunic), showing that popularity and value are two separate stories.
- **Tunic is a standout high-value item.** Despite a below-average purchase count (61), Tunic had the highest average purchase amount by a wide margin ($319.91) — nearly double most other items.
- **Price does not predict satisfaction.** Purchase Amount and Review Rating showed essentially no correlation (r = 0.017). A scatter plot confirmed this visually — ratings from 1–5 were evenly scattered across the full spending range, with no upward or downward trend. Cheap and expensive items are rated similarly.
- **Credit Card purchases average slightly higher spend than Cash** ($160.37 vs $152.70, about a 5% gap), and are used somewhat more often (1,770 vs 1,630 transactions).

![Top items by count and average spend](images/top_items_chart.png)
![Purchase amount vs review rating](images/correlation_scatter.png)

## 💡 So what? (Recommendation)
Since price doesn't predict customer satisfaction, a retailer shouldn't assume premium-priced items are automatically higher-quality in customers' eyes — satisfaction likely depends on other factors (fit, product quality, expectations) that would be worth investigating separately, such as through returns data or written review text. Meanwhile, standout high-value items like Tunic could be worth featuring in targeted upselling, since customers are already demonstrating willingness to spend more on them despite lower purchase frequency.

## 📁 Repo structure
```
├── Fashion_Retail_Sales_Analysis.xlsx   # Full analysis with PivotTables and charts
├── images/                              # Exported chart images
└── README.md
```

## 🔗 Links
- [Dataset on Kaggle](https://www.kaggle.com/datasets/fekihmea/fashion-retail-sales)
