# Amazon_Vine_Analysis
## Overview of the Analysis
Use PySpark to perform the ETL process to extract the dataset, transform the data, connect to an AWS RDS instance, and load the transformed data into pgAdmin. Next, use PySpark, Pandas, or SQL to determine if there is any bias toward favorable reviews from Vine members in the dataset.

## Results
- A dataset of 2,302,401 reviews on Outdoor products was pulled from AWS. 

- From this dataset, a vines_df was created with the following columns:
    * review_id
    * star_rating: the product is rated 1-5
    * helpful_votes
    * total_votes
    * vine
    * verified_purchase

- The DataFrame was filtered and records counted based on several questions: 
    * How many Vine reviews and non-Vine reviews are there? 
    ![image of code to count number of vine reviews](https://github.com/EBolinVA/Amazon_Vine_Analysis/blob/main/Amazon_Vines_Images/Paid_Vine_Reviews.png)
    ![image of code to count number of non-vine reviews](https://github.com/EBolinVA/Amazon_Vine_Analysis/blob/main/Amazon_Vines_Images/Unpaid_Vine_Reviews.png)

The next image answers these two questions:
    * How many Vine reviews were 5 stars?
    * What percentage of Vine reviews were 5 stars?
    ![image of code to count and calculate percentage of vine 5 star reviews](https://github.com/EBolinVA/Amazon_Vine_Analysis/blob/main/Amazon_Vines_Images/Paid5star_pct.png)

The final piece of code answers the last question:
    * What percentage of non-Vine reviews were 5 stars?
    ![image of code to count and calculate percentage of non-vine 5 star reviews](https://github.com/EBolinVA/Amazon_Vine_Analysis/blob/main/Amazon_Vines_Images/Unpaid5star_pct.png)


## Summary

