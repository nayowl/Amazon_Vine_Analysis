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
The dataset will be extracted to DataFrame and transformed to 4 different DataFrames that match table in pgAdmin.  The 4 table that will be transformed is customer_table that has information about customer id and count of review customer had in the dataset, product_table that has information about product id and name of the product, review_id_table that has information about review id, customer id, product id, product parent and review data, and last is the vine table that has information about review id, star rating of the product,helpful votes, total votes, flag that determine if the review is vine or not,and flag for verified purchase. Figure 1 will show us the transformed data that has been successfully loaded in to pgAdmin Table.

<p align="center">
    <img src="https://user-images.githubusercontent.com/88597187/145683325-6e17246b-bc56-4cc1-ae2a-36c68bcad903.png" width="400" height="200"/>
     <img src="https://user-images.githubusercontent.com/88597187/145683332-799f5547-c08e-4f8c-9950-72a00aa78e5e.png" width="400" height="200"/>
  <img src="https://user-images.githubusercontent.com/88597187/145683335-c34ee2c1-cbc6-4e06-8d67-d0dd7d65d9c8.png" width="400" height="200"/>
    <img src="https://user-images.githubusercontent.com/88597187/145683330-96a3fa66-3211-423c-9866-37e455d87a86.png" width="400" height="200"/>
  
</p>
<p align="center">
  <sub>Figure 1 Tables in pgAdmin</sub>
</p>

