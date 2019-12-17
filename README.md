# amazon-reviews
## About the project:<br>
This project is for GWU 2019 summer DNSC 6278 Big Data Analytics final project. The goal of the project is to identify one or more question of interest based on a large dataset and use the tools learned in class(MapReduce, Hadoop Streaming, PIG, Hive, Spark - all APIs) to produce an interesting result.

## About the data:<br>
Our group choose Amazon Customer Reviews Dataset which is documented in https://registry.opendata.aws/amazon-reviews/
. The data which is over 32G includes over 130+ million customer reviews available in TSV files in the amazon-reviews-pds S3 bucket in AWS US East Region. This dataset was constructed to represent a sample of customer evaluations and opinions, variation in the perception of a product across geographical regions, and promotional intent or bias in reviews.

## Table of Content
Data Sourcing and Ingesting
Exploratory Analysis and Data visualization
Classification Modeling

## Project Outline
1. By loading the data from S3 Bucket to a spark dataframe, we managed to handle 50GB dataset on the cloud(AWS EMR)
2. After cleaning the data with missing values and outliers, we visualized the distribution and trend, built common word cloud and generated several insights such as Vine members tend to give lower ratings compared to non-members, the lowest star rating shows higher percentage of helpfulness.
3. Then we did the sentiment analysis with python Lexicon package, converted the review text to a sentiment score(closer to 1, more positive; closer to 0, more negative). The sentiment score is in accordance with the star rating.
4. In the last step, we successfully built a model that classifies the helpfulness of one review. The purpose of the model is to automaticaaly identify helpful reviews and display it on top of the [Customer review section] of the Amazon website, which will greatly enhance the experience of new customers who want to get the information of the product before they make the purchase.

## Detailed approach includes:
1) binarize the helpful count to our target variable,
2) used StringIndexer to encode categorical variable,
3) used VectorAssembler to combine features, and
4) built a pipleline to combine these process with 3 different algorithems(Logistic Regression, Random Forest and Gradient Boosting Decision Tree). Random Forest Classifier shows the highest accuracy of 0.75.
