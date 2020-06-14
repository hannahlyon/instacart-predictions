# Predicting Instacart repurchases
Instacart is a grocery delivery and pick up service where users can place orders online and have their groceries delivered the same day. Our goal is to apply machine learning to **predict whether a product once ordered by an Instacart user was _reordered_**, ultimately helping answer the question "which products are likely to be in a user's next order?"  Here, we present our methods for data cleaning, feature engineering, model training, and model selection.

**Team members**: Hannah Lyon, Andy Cheon, Marine Lin

## Data
Data were acquired from the [Instacart Market Basket Analysis](https://www.kaggle.com/c/instacart-market-basket-analysis/)  Kaggle competition. Consisting of 3 million orders from 200,000 users, this dataset was split into six tables.  We joined these tables to produce one full training set.

## Feature Engineering
We performed feature engineering by adding the following columns:
  - `weekend`: Binary feature indicating if an order was placed over the weekend
  - `department_is_staple`: Binary feature indicating if an item is a staple item. E.g. bread, milk, eggs
  - `product_is_organic`: Binary feature indicating if a product is organic

Needless to say, this is a very basic set of engineered features.  Given the rich amount of data Instacart provided, we plan to include many more features derived from product, user, and product-user specific data.

## Models
Using scikit-learn's `Pipeline` tool, we fit five models to the training data: Random Forest, Logistic Regression, Naive Bayes, KNN, and SVM.

With these models, we achieved the following F1 scores:
| Model                | F1 Score|
| -------------------- | ------- |
| **Random Forest**        | **0.694**   |
| Logistic Regression  | 0.488   |
| Naive Bayes          | 0.487   |
| KNN          		   | 0.638   |
| SVM          		   | 0.667   |

## Business impact and implications
We have trained a model that predicts whether or not a product ordered by a particular user was a reordered product.  This could provide Instacart insight into which products tend to be reordered given past user behavior, thus potentially helping the company decide who receives targeted recommendations for which products.

## Future improvements
Our model does not take into account sequence information (e.g. user's previous orders, _in chronological order_). Considering sequence information would allow us to use, for example, the _apriori_ algorithm to predict the user's next ordered product via association learning.  Lastly, our models would likely be greatly improved if we create more customer-specific and customer-product specific features.
