# DSA-Project---Amazon-Product-Review

## Project Purpose
The project aimed to analyze product and customer review data to generate insights that can guide product improvement, marketing strategies, and customer engagement

## Data Source:
The dataset was gotten by scraping information from Amazon product pages, including 
• Product details: name, category, price, discount, and ratings 
• Customer engagement: user reviews, titles, and content 
• Each row represents a unique product, with aggregated reviewer data stored as comma-separated values 

## Data Dictionary: 
-  Product_id - unique identifier for each product
-  Product_name - name of product as gotten from the website	
-  Category - the category of the product
-  Discounted_price - price discounted or deducted from actual price in Indian rupees
-  Actual_price - the actual price of the product in Indian rupees
-  Discount_percentage	- percentage of discount given for the product
-  Rating - the average rating given by customers on the product
-  Rating_count - the total number of reviews on the product
-  About_product	- description of the product uses and features
-  User_id - Customers unique identifier	
-  User_name	- customers name 
-  Review_id	- unique identifier for review
-  Review_title - title given to review by customers
-  Review_content	- reviews contents written by customers
-  Img_link - link to image of the product
-  Product_link - link to the product on the website


## Assumptions: 
- Missing values found in the rating column to changed to 0.
- The category column was separated into its main category and sub-categories using the delimiter to convert the text to column.
- Each row was considered unique as the remove duplicates returned 0, because each row was unique in the information provided.
- Note any assumptions made during the analysis, such as data cleaning rules or handling of missing values.
- Irrelevant columns not needed for analysis such as about_product will be hidden or remove

## Analysis Steps:
### Exploratory Data Analysis

### 
1. What is the average discount percentage by product category?
   
   Average discount percentage by product category was gotten using pivot table.
   
2. How many products are listed under each category?

   Count of products in each category by creating a pivot table:
    Rows: Category (Main)
    Values: Product Name → set to Count

3. The total number of reviews per category -

   Pivot Table:
    Rows: Category
    Values: Rating Count → Sum

4. Products have the highest average ratings -

    Sorted the dataset by the Rating column (descending)
    Pick top entries
     3 products had a rating of 5.0 
   
5. What is the average actual price vs the discounted price by category?

   Using a pivot table:
  Rows: Category
  Values: Actual Price → Average
  Discounted Price → Average
 
7. Which products have the highest number of reviews?

   Sort Rating Count column in the dataset in descending order
   About 5 products as the highest
   
8. How many products have a discount of 50% or more?

  Added a conditional column (Discount above average): =IF(Discount_percentage >= 50, "Yes", "No")
  
  Then used a COUNTIF('Discount above average','Yes')
  
  
8. What is the distribution of product ratings (e.g., how many products are rated 3.0, 
    4.0, etc.)?

  Using a pivot table:
  Rows: Rating
  Values: Product name → Count

  An histogram chart was created using the table and the rating distribution is rightly skewed.
  
  More product has high rating compared to lower ratings.
   
9. What is the total potential revenue (actual_price × rating_count) by category?

  Total potential revenue by category (Actual Price × Rating Count)
  
  Added calculated column (Potential revenue): =Actual Price * Rating Count

  Using Pivot Table:
  Rows: Category
  Values: Potential Revenue → Sum
  
10. What is the number of unique products per price range bucket (e.g., <₹200, 
₹200–₹500, >₹500)? 
15. How does the rating relate to the level of discount? 
16. How many products have fewer than 1,000 reviews? 
17. Which categories have products with the highest discounts? 
18. Identify the top 5 products in terms of rating and number of reviews combined.

Document the key steps in your analysis, including formulas used, pivot tables created, or charts generated. 

A dashboard was created using Microsoft Excel [link](
