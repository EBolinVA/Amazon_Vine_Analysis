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
Over 2 million reviews were filtered down to a dataset of 39,976 reviews that had at least 20 votes, and of those votes, at least half were considered to be helpful votes. 

From that dataset of 39,976 reviews, there were 107 reviews where "vine" = 'Y': a paid Vine review. The 39,869 remaining reviews were unpaid, or non-Vine, reviews. Already we can see that there is an imbalance in the classes of data. 

Of the 39,976 Vine and non-Vine reviews, there were 21,061 reviews with 5-star ratings.

Of the 21,061 reviews with 5-star ratings, 56 were Vine reviews. In other words, 0.27% of the Vine reviews had a 5-star rating.

Of the 21,061 reviews with a 5-star rating, 21,005 were non-Vine reviews. 99.73% of the non-Vine reviews were 5-star rated.

## Further consideration
I would run the statistics again to calculate percentages of reviews within like types:
(5-star Vine reviews/total Vine reviews)* 100
(5-star non-Vine reviews/total non-Vine reviews)* 100
