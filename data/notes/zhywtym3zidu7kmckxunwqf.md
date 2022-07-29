
Instead of selecting data into a data frame or dealing with data in that manner,
Just select the data into [[s.df.json]] straight from the database so that you
can use the data in the app as pure json as needed and if you need to push data
back into the database you could easily read the json into pandas and push that
to the SQL db or maybe even just send the json string back!
