# Real Estate Price Prediction

This project was implemented within Wargaming Forge educational course. The main goal is to predict price of a rental property and provide insights to the user so he will be able to figure out which of them are undervalued.

The project conditions were close to real cases. The main challenges were:
- Pull out the main requirements from the "customer"
- Find the datasource and fetch data from them
- Clean and prepare data for the models
- Make a transaprent model. It means that the customer should be able to understand why the model provides such results
- Choose the right metrics
- Vizualization of the results and user-friendly exaplnation

During the exploration phase, linear models were chosen as the most explainable approach. The most suitable one - Huber regressor. Our data contain a lot of outliers and Huber is the most robust linear model for them. [Huber documentation](http://scikit-learn.org/stable/modules/generated/sklearn.linear_model.HuberRegressor.html "skLearn documentation")

In order to make the model interpretable, the final feature set was decreased by Lasso model. The main idea is that the extra feature weights will be nullified by L1 regularization. In fact, there were more than 150 features and after applying Lasso model only 18 features left. The features and their coefficients in the Huber model can be used to explain the results. [eli5 documentation](https://eli5.readthedocs.io/en/latest/ "eli5 documentation")

The final predictions were visualized on Tableau Map. It's a tool for displaying geographic data in the most user-friendly way - on the city map.

![The Map](https://user-images.githubusercontent.com/8157859/41438236-47f87f20-702f-11e8-9587-c7d6e5d87648.png)


Also there is a popup which provides an explanation:
![The popup](https://user-images.githubusercontent.com/8157859/41438235-47db9a4a-702f-11e8-94c7-0fe31c1279e5.png)
