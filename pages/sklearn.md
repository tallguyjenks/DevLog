---
tags: library
---

- ^^Kaggle ML Course^^
	- Reading and looking at the shape of the data
		-
		  ```python
		  import pandas as pd
		  
		  melbourne_file_path = '../input/melbourne-housing-snapshot/melb_data.csv'
		  melbourne_data = pd.read_csv(melbourne_file_path) 
		  melbourne_data.columns
		  # The Melbourne data has some missing values (some houses for which some variables weren't recorded.)
		  # We'll learn to handle missing values in a later tutorial.  
		  # Your Iowa data doesn't have missing values in the columns you use. 
		  # So we will take the simplest option for now, and drop houses from our data. 
		  # Don't worry about this much for now, though the code is:
		  
		  # dropna drops missing values (think of na as "not available")
		  melbourne_data = melbourne_data.dropna(axis=0)
		  # Seleting the target prediction
		  y = melbourne_data.Price
		  # Choosing features to help you predict the target
		  melbourne_features = ['Rooms', 'Bathroom', 'Landsize', 'Lattitude', 'Longtitude']
		  # Concention is that the data is called X
		  X = melbourne_data[melbourne_features]
		  X.describe()
		  X.head()
		  
		  ```
	- Define the Model
		-
		  ```python
		  from sklearn.tree import DecisionTreeRegressor
		  
		  # Define model. Specify a number for random_state to ensure same results each run
		  melbourne_model = DecisionTreeRegressor(random_state=1)
		  
		  # Fit model
		  melbourne_model.fit(X, y)
		  print("Making predictions for the following 5 houses:")
		  print(X.head())
		  print("The predictions are")
		  print(melbourne_model.predict(X.head()))
		  
		  ```
	- Mean Absolute Error
		-
		  ```python
		  from sklearn.metrics import mean_absolute_error
		  
		  predicted_home_prices = melbourne_model.predict(X)
		  mean_absolute_error(y, predicted_home_prices)
		  ```
	- Split data into test and validation sets
		-
		  ```python
		  from sklearn.model_selection import train_test_split
		  
		  # split data into training and validation data, for both features and target
		  # The split is based on a random number generator. Supplying a numeric value to
		  # the random_state argument guarantees we get the same split every time we
		  # run this script.
		  train_X, val_X, train_y, val_y = train_test_split(X, y, random_state = 0)
		  # Define model
		  melbourne_model = DecisionTreeRegressor()
		  # Fit model
		  melbourne_model.fit(train_X, train_y)
		  
		  # get predicted prices on validation data
		  val_predictions = melbourne_model.predict(val_X)
		  print(mean_absolute_error(val_y, val_predictions))
		  ```
	-
		-
	-
		-
	-
		-
-