# Amazon_Vine_Analysis
## 1. Overview
The Amazon Vine program is a service that allows manufacturers and publishers to receive reviews for their products. SellBy pay a small fee to Amazon and provide products to Amazon Vine members, who are then required to publish a review. This project will analyze the existing Amazon reviews written by members of the paid Amazon Vine program and determine if there is any bias toward favorable reviews from Vine members and whether is it worthed for SellBy to use Amazon vine program. The following tasks will be performed in this analysis:
* Use PySpark to perform the ETL process to extract the dataset
* Transform the data and  connect to an AWS RDS instance
* Load the transformed data into pgAdmin
* Use Pyspark to  determine if there is any bias toward favorable reviews from Vine members in the dataset

## 2.Resources
Data Source: https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Baby_v1_00.tsv.gz

Software: PySpark, pgAdmin, AWS RDS

## 3. Result
### Transform Data and Connect to an AWS RDS Instance
The dataset will be extracted to DataFrame and transformed to 4 different DataFrames that match table in pgAdmin.  The 4 table that will be transformed is customer_table that has information about customer id and count of review customer had in the dataset, product_table that has information about product id and name of the product, review_id_table that has information about review id, customer id, product id, product parent and review data, and last is the vine table that has information about review id, star rating of the product,helpful votes, total votes, flag that determine if the review is vine or not,and flag for verified purchase. Figure 1 will show us the transformed data that have been successfully loaded in to pgAdmin Table.

<p align="center">
    <img src="https://user-images.githubusercontent.com/88597187/145683325-6e17246b-bc56-4cc1-ae2a-36c68bcad903.png" width="400" height="200"/>
     <img src="https://user-images.githubusercontent.com/88597187/145683332-799f5547-c08e-4f8c-9950-72a00aa78e5e.png" width="400" height="200"/>
  <img src="https://user-images.githubusercontent.com/88597187/145683335-c34ee2c1-cbc6-4e06-8d67-d0dd7d65d9c8.png" width="400" height="200"/>
    <img src="https://user-images.githubusercontent.com/88597187/145683330-96a3fa66-3211-423c-9866-37e455d87a86.png" width="400" height="200"/>
  
</p>
<p align="center">
  <sub>Figure 1 Tables in pgAdmin</sub>
</p>

### Vine Review


<p align="center">
    <img src="https://user-images.githubusercontent.com/88597187/145694401-3a1a5e17-287c-43a5-9a99-80eb854f323c.png" width="600" height="75"/>
     <img src="https://user-images.githubusercontent.com/88597187/145694408-b428dcb8-7cf0-4d4e-8fef-b4b8931da996.png" width="300" height="75"/>
  
</p>
<p align="center">
  <sub>Figure 2 Vine review Summary </sub>
</p>


Figure 2  show us the summary of Vine Review from the vine_table. From the summary we can conclude:
* There are 463 vine review and 25094 non vine review
* 202 of the vine reviews were 5 stars and  12033 of  non-vine reviews were 5 stars
* 43.63% vine reviews were 5 stars
* 47.95% non-vine review were 5 stars

## 4. Summary

This project main purpose is to determine if there is any bias toward favorable reviews from vine members. The data is extracted from reviews that percentage of  helpful_votes greater than 50% to make sure the review is really helpful for customer to make decision from both vine members and non-vine members. From Figure 2 we can see that the percentage 5 stars review for vine member is 43.63% while for the non-vine members is 47.95%. From this we can conclude that there is no bias toward favorable review from vine members , since there is no significant different of 5 star review and the review for non-vine members even slighlty higher 4.32% than vine members.

Additionally, to add more detail we can perform additional query in 4 star review and 3 star review to make sure that there is no bias in the reviews for 4 and 3 stars. We can perform the query in another category too , to make sure that other category has the same result with this dataset. 



