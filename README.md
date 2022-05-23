# Random-Forest
Overview:

a small project about implementing random forest on some medical data (called pima-indians-diabetes) in help of GridSearchCV and RandomForestClassifier 

details:

Via Scikit-learn library's model selection, we divided the data set into three parts, implemented the model on the data, finding the accuracy, and plotting the confusion table and the decision tree. We want to pay your attention to that optimizing a ML model is sometimes done by experiments not by science especially when a model has many parameters like in Random Forest. However not all parameters are equally important. n_estimators, the number of trees in the forest, and max_features, the number of features for splitting at each leaf node, are the most important in this algorithm. There are some other parameters like max_depth (the maximum number of levels in each decision tree), min_samples_splitis (the minimum number of data points placed in a node before the node is split),  min_samples_leaf (min number of data points allowed in a leaf node), and bootstrap (a method for sampling data points) . Trying all kind of combinations of all these parameters is almost an impossible task. Fortunately, there are there are two techniques for narrowing down these compination:
1.	RandomForestClassifier:
It narrows down the search space sample (no give an accurate answer). It has two important parameters, n_iter, which manage the number of unique combinations to try, and cv, the number of cross validation folds.
2.	GridSearchCV
It gives more accuracy but slow computationally because it is greedy. It has one important parameter called cv (number folds) which we stratified it to balance our data.

Our approach is to combine between the two, firstly using RandomForestClassifier narrowing down a wide range of the recommended ranges (for ex. default nr trees is 10 we tried 5 more or fewer tries) for the important parameters, then using GridSearchCV to drive in the narrowed ranges of the respective parameters. This hybrid approach gave a little better result than just depending on the result of one of the two techniques.


Source:
1. data set
 https://www.kaggle.com/uciml/pima-indians-diabetes-database

