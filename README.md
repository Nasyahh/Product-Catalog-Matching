# Product-Catalog-Matching
SequenceMatcher library to find matching names between two datasets
## Overview
This project aims to *find out how much fertilizer the company actually sold* based on the point of sales data and the product catalog data. The point of sales data contains the product names that were sold by the company's distributors. The product catalog data contains the product names, manufacturers, and main compositions of the products that the company offers.

The main challenge of this project is that the product names in the point of sales data are *not in the same format* as the product names in the catalog data. For example, the same product might have different spellings, abbreviations, or variations in the point of sales data. This makes it difficult to match the sold products with the catalog products by using exact string matching.

To overcome this challenge, this project uses the *SequenceMatcher library* in *Python* to measure the *similarity* between the product names and find the best matches. The SequenceMatcher library compares two sequences of any type and computes a score that represents how similar they are. The higher the score, the more similar the sequences are.

## Data
The data consists of two datasets: the *product catalog data* and the *point of sales data*. The product catalog data has 187 rows and 3 columns, which are:

- *Product SKU*: The name of the product in the catalog.
- *Brand*: The name of the manufacturer of the product in the catalog.
- *Type*: The main composition of the product in the catalog.

The *point of sales data* has 44002 rows and 1 column, which is:

- *product_name*: The name of the product that was sold in the transaction.

## Method
The method used for this project is as follows:

- First, the product names in both datasets are *cleaned* and *normalized* by removing punctuation, whitespace, and converting to lowercase.
- Second, the product names in the point of sales data are *matched* with the product names in the catalog data by using the SequenceMatcher library. For each product name in the point of sales data, the best match in the catalog data is found by using the highest similarity score. A threshold of *0.6* is used to determine if the match is valid or not. If the similarity score is above or equal to 0.6, the match is considered valid. If the similarity score is below 0.6, the match is considered invalid.
- Third, the matched products are *categorized* into two groups: the *existing category* and the *new category*. The existing category contains the products that have a valid match in the catalog data. The new category contains the products that do not have a valid match in the catalog data.

## Result
The result of the project is as follows:

- Out of the *44002 products* in the point of sales data, *3437 products* were matched with the catalog data and *40579 products* were not matched with the catalog data.
- The *3437 products* in the existing category represent *7.8%* of the total products in the point of sales data. The *40579 products* in the new category represent *92.2%* of the total products in the point of sales data.
