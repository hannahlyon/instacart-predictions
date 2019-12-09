# instacart prediction
Instacart is a grocery delivery and pick up service where users can 
place orders online and have their groceries delivered the same day.
We have access to their data which is consists of 3M orders from 200K users.
Our goal is to apply machine learning to predict whether a product ordered by an Instacart user was reordered.

Group member: Hannah Lyon, Andy Cheon, Marine Lin

# Main Goal
How well can we predict whether a product ordered by an Instacart user was reordered?

# Feature Engineering
Data Processing: weekends: Binary feature indicating if an order was placed over the weekend

Staple:Binary feature indicating if an item is a staple item. E.g. bread, milk, eggs

Organic: Binary feature indicating if a product is organic

# Models
Models applied: KNN,Random Forest,SVM, Logestic regression, Naive Bayes

Best Model: Random Forest

North Star Metric: Weighted F1 score


Best Model north star metric: weighted F1 score: 0.69

# Impact
Decent prediction on whether or not a product ordered by a particular user was a reordered product

Provides insight into which products tend to be reordered

Could provide suggested products to users who open the app

# future improvements:
Does not take into account sequence information (user's previous orders, in chronological order)

Create more customer-specific and customer-product specific features

Could modify prediction to be user's next ordered product; try apriori algorithm (association learning)
