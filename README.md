Market Basket Analysis – Groceries Dataset
 Project Overview

This project performs Market Basket Analysis on a grocery transactions dataset to discover product purchasing patterns and association rules.

The goal is to identify:

Frequently purchased items

Frequently purchased product pairs

Strong association rules using Support, Confidence, and Lift

This helps businesses improve:

Product placement

Cross-selling strategies

Promotional campaigns

Inventory planning

📂 Dataset

File Used: Groceries_dataset.csv

Dataset Columns:

Member_number – Unique customer ID

Date – Transaction date

itemDescription – Purchased product

Each row represents one product in a transaction.

 Technologies Used

Python

Pandas

Matplotlib

itertools

CSV Export

 Data Preprocessing

Removed missing values

Stripped whitespace from item names

Grouped items by Member_number to create transactions

Converted transactions into item sets for frequency calculation

 Step 1: Single Item Support

Support Formula:

Support(A)= Transactions containing A / Total Transactions

 Top 5 Most Frequent Items
Item	Support
whole milk	0.458
other vegetables	0.377
rolls/buns	0.350
soda	0.313
yogurt	0.283

 Insight:

Whole milk is the most purchased product.

Dairy and bakery items are dominant.

Step 2: Item Pair Support

Calculated all 2-item combinations using itertools.combinations().

 Top 5 Product Pairs
Item Pair	Support
(other vegetables, whole milk)	0.191
(rolls/buns, whole milk)	0.179
(soda, whole milk)	0.151
(whole milk, yogurt)	0.151
(other vegetables, rolls/buns)	0.147

 Insight:

Whole milk appears in most top product pairs.

Strong cross-selling opportunity around dairy products.

 Step 3: Association Rule Mining

Metrics Used:

1️ Confidence
Confidence(A→B)=  Support(A,B)/Support(A)
                 
​2️ Lift
Lift(A→B)= Confidence(A→B)/Support(B)

 Strong Rules Criteria

Rules filtered using:

Confidence ≥ 0.4

Lift ≥ 1.2

Example Strong Rule:

Antecedent	Consequent	Confidence	Lift
rubbing alcohol	butter milk	0.60	9.24

 Note:
Some rules show very high lift due to very low support. These may not be practically useful in business decisions.

 Visualizations

 Top 10 Product Pairs (Horizontal Bar Chart)

 Confidence vs Lift Scatter Plot

 Output Files

The following files were exported:

item_support.csv

pair_support.csv

association_rules.csv

These files contain:

Item support values

Pair support values

Strong association rules

📁 Project Structure
.
│
├── Groceries_dataset.csv
├── item_support.csv
├── pair_support.csv
├── association_rules.csv
├── Market_Basket_Analysis.ipynb
└── README.md
 Business Applications

✔ Product Bundling
✔ Cross-Selling Recommendations
✔ Store Layout Optimization
✔ Promotional Campaign Design
✔ Recommendation Systems

 Future Improvements

Apply minimum support threshold before rule generation

Use Apriori or FP-Growth algorithm

Generate 3-item combinations

Implement interactive dashboard

Deploy recommendation system
