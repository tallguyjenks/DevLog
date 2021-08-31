---
title: pandas
tags: library
---

- **Resources**
  done:: 1623346783569
	- [Calm Code Pandas Pipe](https://calmcode.io/pandas-pipe/pipe.html)
	- [25 Pandas Functions You Didn’t Know Existed | P(Guarantee) = 0.8](https://towardsdatascience.com/25-pandas-functions-you-didnt-know-existed-p-guarantee-0-8-1a05dcaad5d0)
- **Examples**
  collapsed:: true
	-
	  ```python
	  # Libs
	  import pandas as pd
	  	      
	  # Instead of using CSV module this can make a dataframe out of your csv file
	  df = pd.read_csv('data.csv')
	  
	  # kind of like the skimr function in R to describe the dataset with common statistics
	  df.describe()
	  	      
	  # Preview of our data
	  df.head(10)
	  	      
	  # Preview of our data
	  df.tail(10)
	  	      
	  # Get the shape of the data frame (Rows, Columns)
	  # Attribute not a method so no parens needed
	  df.shape
	  	      
	  # Get info about the data frame fields
	  # This is a method so parens are needed
	  # Object types are usually strings
	  df.info()
	  	      
	  # makes is so the printed dataframe above with the `df` call cell displays 85 total columns
	  pd.set_option('display.max_columns',85)
	  # makes is so the printed dataframe above with the `df` call cell displays 85 total rows
	  pd.set_option('display.max_rows',85)
	  	      
	  # Load csv schema
	  schema_df = pd.read_csv('data_schema.csv')
	  	      
	  schema_df
	  ```
	-
	  ```python
	      #!/usr/bin/env python
	      # coding: utf-8
	      
	      # # Pandas tutorial with Stackoverflow data
	      # 
	      # > This tutorial is using data from the stack overflow developer survey that can be found at the following link:
	      # [Developer Survey List](https://insights.stackoverflow.com/survey)
	      # Libs
	      import pandas as pd
	      # Instead of using CSV module this can make a dataframe out of your csv file
	      df = pd.read_csv('data.csv')
	      # Preview of our data
	      df.head(10)
	      # Preview of our data
	      df.tail(10)
	      # Get the shape of the data frame (Rows, Columns)
	      # Attribute not a method so no parens needed
	      df.shape
	      # Get info about the data frame fields
	      # This is a method so parens are needed
	      # Object types are usually strings
	      df.info()
	      # makes is so the printed dataframe above with the `df` call cell displays 85 total columns
	      pd.set_option('display.max_columns',85)
	      # makes is so the printed dataframe above with the `df` call cell displays 85 total rows
	      pd.set_option('display.max_rows',85)
	      # Load csv schema
	      schema_df = pd.read_csv('data_schema.csv')
	      schema_df
	      df['Hobbyist']
	      people = {
	          "first": ["Corey", 'Jane', 'John'], 
	          "last": ["Schafer", 'Doe', 'Doe'], 
	          "email": ["CoreyMSchafer@gmail.com", 'JaneDoe@email.com', 'JohnDoe@email.com']
	      }
	      people['email']
	      peeps = pd.DataFrame(people)
	      peeps
	      peeps['email']
	      peeps.email
	      peeps[['last','email']]
	      peeps.columns
	      # loc = location
	      # iloc = integer location
	      peeps.iloc[[0, 1], 2] # return the first and second record and only the 3rd field of those records
	      df['email']
	      df.Hobbyist.value_counts()
	      # # Video #3
	      # ## Python Pandas Tutorial (Part 3): Indexes - How to Set, Reset, and Use Indexes
	      # 
	      #[video3](https://youtu.be/W9XjRYFkkyw?list=PL-osiE80TeTsWmV9i9c58mdDCSskIFdDS)
	      # 
	      people = {
	          "first": ["Corey", 'Jane', 'John'], 
	          "last": ["Schafer", 'Doe', 'Doe'], 
	          "email": ["CoreyMSchafer@gmail.com", 'JaneDoe@email.com', 'JohnDoe@email.com']
	      }
	      df = pd.DataFrame(people)
	      df.set_index('email')
	      df
	      df.set_index('email', inplace=True) # make it so changes overwrite the df
	      df
	      df.loc['CoreyMSchafer@gmail.com']
	      df.iloc[0]
	      get_ipython().run_line_magic('lsmagic', '')
	      get_ipython().run_cell_magic('html', '', '<b>hello there</b>')
	      get_ipython().run_cell_magic('bash', '', 'ls -la')
	      get_ipython().run_line_magic('ls', '-la')
	      get_ipython().run_line_magic('ls', '-la')
	      get_ipython().run_line_magic('ls', '-la')
	      
	      ```
- **Pandas Pipe**
  collapsed:: true
	-
	  ```python
	  import pandas as pd
	  
	  df = pd.read_csv('https://calmcode.io/datasets/bigmac.csv')
	  
	  def set_dtypes(dataf):
	      return (dataf
	              .assign(date=lambda d: pd.to_datetime(d['date']))
	              .sort_values(['currency_code', 'date']))
	  
	  def remove_outliers(dataf):
	      min_row_country=32
	      countries = (dataf
	                  .groupby('currency_code')
	                  .agg(n=('name', 'count'))
	                  .loc[lambda d: d['n'] >= min_row_country]
	                  .index)
	      return (dataf
	              .loc[lambda d: d['currency_code'].isin(countries)])
	  
	  df.pipe(set_dtypes).pipe(remove_outliers)
	  ```
	- Can use logging decorators with [[functools]] to log data changes:
		-
		  ```python
		  from functools import wraps
		  import datetime as dt
		  
		  def log_step(func):
		      @wraps(func)
		      def wrapper(*args, **kwargs):
		          tic = dt.datetime.now()
		          result = func(*args, **kwargs)
		          time_taken = str(dt.datetime.now() - tic)
		          print(f"just ran step {func.__name__} shape={result.shape} took {time_taken}s")
		          return result
		      return wrapper
		  ```
-