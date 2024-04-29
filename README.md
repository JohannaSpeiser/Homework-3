# Homework-3
Personal Info
a. Johanna Speiser
b. 2380023
c. jospeiser@chapman.edu
d. cpsc-392-02
e. Homework 3

ChatGPT:

1
What is wrong with this? """(ggplot(behav_data, aes(x = "current_income", y = "prop_ad_clicks"))) + geom_point()
"""

2
What does this mean? """PlotnineError: "Could not evaluate the 'y' mapping: 'prop_ad_clicks' (original error: name 'prop_ad_clicks' is not defined)"
"""

3
I'm getting this error message """ValueError: could not convert string to float: 'man'""" for this code """X = behav_data[predictors]

z = make_column_transformer((StandardScaler(), predictors),
remainder = "passthrough")

# z-score
pre = make_column_transformer((StandardScaler(), contin),
(OneHotEncoder(), "gender"),
remainder = "passthrough")

km = KMeans(n_clusters = 4)
pipe = Pipeline([("z", z), ("clust", km)])

labels = pipe.fit_predict(X)

print(silhouette_score(X, pipe.predict(X)))

X["clusters"] = labels

print(ggplot(X, aes(x = "energy", y = "danceability", color = "factor(clusters)" )) +
geom_point() + theme_minimal() + labs(x = "Energy", y = "Danceability",
title = "KMeans Clustering Resultsfor K = 4", color = "Clusters"))

print(ggplot(X, aes(x = "energy", y = "valence", color = "factor(clusters)" )) +
geom_point() + theme_minimal() + labs(x = "Energy", y = "Valence",
title = "KMeans Clustering Results for K4", color = "Clusters"))

print(ggplot(X, aes(x = "valence", y = "danceability", color = "factor(clusters)" )) +
geom_point() + theme_minimal() + labs(x = "Valence", y = "Danceability" ),
title = "KMeans Clustering Results for K = 4", color = "Clusters")"""

Why?
4
What does this mean? """ValueError Traceback (most recent call last)
/usr/local/lib/python3.10/dist-packages/sklearn/compose/_column_transformer.py in _fit_transform(self, X, y, func, fitted, column_as_strings)
657 try:
--> 658 return Parallel(n_jobs=self.n_jobs)(
659 delayed(func)(
"""

5
How can I change this so that it expects 1D? """ValueError                                Traceback (most recent call last)
/usr/local/lib/python3.10/dist-packages/sklearn/compose/_column_transformer.py in _fit_transform(self, X, y, func, fitted, column_as_strings)
    669         except ValueError as e:
    670             if "Expected 2D array, got 1D array instead" in str(e):
--> 671                 raise ValueError(_ERR_MSG_1DCOLUMN) from e
    672             else:
    673                 raise

ValueError: 1D data passed to a transformer that expects 2D data. Try to specify the column selection as a list of one item instead of a scalar.
"""

6
What does "named_steps" do in this code? """pcaDF = pd.DataFrame({"expl_var" : behav_data.named_steps["pca"].explained_variance_ratio_,
"pc": range(1,5), "cum_var": behav_data.named_steps["pca"].explained_variance_ratio_.cumsum()})"""

7
What does this error message mean? """ValueError: All arrays must be of the same length
"""

8
How can I get a PCA to give me the largest two PCs?
—
​​But what are the two largest ones called?
—
Yes but does my code know that? How should I name them if I want to use them in a scatter plot?

9
What does this mean? """TypeError: 'PCA' object is not subscriptable"""
10
What does this mean """ValueError: Columns must be same length as key""" with respect to this """behav_data[["pc1", "pc2"]] = pd.DataFrame(pipe_behav_data.transform(behav_data[contin]))""" ?

11
What does this mean? """d[["pc1", "pc2"]] = pd.DataFrame(pipe_pca.transform(d[names]))"""

