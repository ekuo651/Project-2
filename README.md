# Project-2

#Title Slide
Machine learning model for stock selection 

#Include the name of the project and group members.
**Andrea Ovelar, Christian Stracke, Emmy Kuo & Weiqing Wang**

## Contents

1. [Our Motivation](!Motivation-&-Summary) 
1. [Our Approach](!Our-Approach)
1. [Methods & Technology](!Methods-&-Technology)


## Motivation & Summary


We are looking to use machine learning model to create a stock portfolio that would outperform the S&P500 benchmark. our hypothesis is that by combining fundamental and technical indicators we could have a portfolio of stocks that outperforms consistently the S&P 500 and rebalances on a monthly basis. This strategy can be easily replicated on different countries. 

Additionally, we applied clustering techniques to the stocks currently in the S&P 500, and then ran our machine learning model on the clusters to further optimize returns. We also explored used recurrent neural networks to predict the trend of individual stocks and the S&P500.



## Our Approach

#Elaborate on the predictive model used, describing why it was the best choice for the data.

### General Stock Selector

Since the goal of the project was to find outperformers on a monthly basis, we selected a supervised learning approach where we would try to classify the constituents of the S&P500 as either outperformers underperformers. We looked at both fundamental indicators and calculated technical indicators for all the constituents dating back to 1995. Stocks that had an average aggregate performance in the top third were determined to be outperformers, and stocks in the bottom third were determined to be underperformers. 

For each month of predictions, we evaluated 12 months of prior data.  The technical indicators, by design, have many redundant/slow changing entries (maximums over a quarter, a year and five years). Several of the fundamental indicators such as ____________________, also do not exhibit rapid change. So despite having a large volume of features, we do not expect for there to be many prevailing rules governing the data. Due to the size and nature of the data, we decided on a random forest approach as it is easy to control overfitting. We decided to use a forest of 20 trees, each with maximum tree depth of 3. By using a Gradient Boosting approach and testing out 6 different learning rates, we found that a learning rate of ____ had the best results. By keepping the forest small, and the trees shallow, we can quickly run and refresh the model as well as prevent overfitting. 

### Incorporating Clusters

Since the premise of finding outperformers relies on the relative performance of other stocks, we decided to cluster the constituents of the S&P500 based on a snapshot of fundamental indicators and then to apply our stock selection model. We did not want to go based off of traditional sectors, but instead to find clusters based on each constituents fundamental data. Therefore, we used K-means clustering, an unsupervised learning model.

We selected the optimal number of clusters to run based on the elbow curve technique where we find the point at which the reduction in loss plateaus. We also used silhouette analysis to determine how well differentiated each cluster would have been based on the number of clusters. 

### Predicting the Market

Without incorporating hedging strategies and derivatives, selecting outperformers can still reflect losses if the entire market is down. The entire market is generally assumed to be an extremely complex system and quite hard to predict. We wanted to select a model that could possibly capture the inherent complexity, thereby decreasing the bias in the bias-variance tradeoff. Since we have S&P500 daily closing prices dating back to 1994, which includes at least 2 market cycles, we decided that to use a recurrent neural network.

## Data

We obtained financial data on fundamental indicators for all the stocks currently in the S&P 500 using the Bloomberg Terminal and Capital IQ. We calculated technical indicators based on the daily closing prices of the S&P 500 and resampled the data on a monthly interval. 

![Presentation_Resources/bloomberg_logo.jpg]


## Methods & Technology

#Describe the exploration and cleanup process.
#Discuss any problems that arose with preparing the data or training the model that you didn't anticipate.
#Discuss the overall training process and highlight anything of interest with the training process: Cloud resources used, training time #required, issues with training.



## Model Evaluation

## Discuss the techniques you used to evaluate the model performance.

We selected the top 20 results from the general classification model and calculated returns based on an equation


## Discussion

## Discuss your findings. Was the model sufficient for the predictive task? If not, why not? What inferences or general conclusions can #you draw from your model performance?



## Postmortem

#Discuss any difficulties that arose, and how you dealt with them.
#Discuss any additional questions or problems that came up but you didn't have time to answer: What would you research next if you had #two more weeks?



#Questions

#Open-floor Q&A with the audience.
