---
collapsed:: false
tags: library
---

- ^^Resources^^
	- [Official Docs](https://docs.prefect.io/core/concepts/schedules.html#clocks)
# Before ETL Process:
collapsed:: true
	-
	  ```python
	  import requests
	  
	  def extract() -> dict:
	      """Use the Open Weather Map API to fetch Boston weather data.
	      Returns:
	          dict: a JSON response of many wheather measurements.
	      """
	  
	      url = "https://api.openweathermap.org/data/2.5/weather"
	  
	      # TODO: Use a real API key. You can get a free one from https://openweathermap.org/
	      response = requests.request(
	          "GET", url, params={"q": "Boston", "appid": "e5ecbcc49e3debeead24d0fe012fb46e"}
	      )
	  
	      return response.json()
	  
	  
	  def transform(response: dict) -> float:
	      """Process the response and extract windspeed information
	      Args:
	          response (dict): Response JSON from extract task
	      Returns:
	          float: Current wind speed
	      """
	      return response.get("wind", {}).get("speed", 0.0)
	  
	  
	  def load(speed: float):
	      """Append data to file
	      Args:
	          speed (float): Windspeed from transform task
	      """
	  
	      with open("windspeed.txt", "a") as f:
	          f.write(str(speed) + "\n")
	  
	  
	  if __name__ == "__main__":
	      # Execute tasks in the right order.
	      response = extract()
	      windspeed = transform(response)
	      load(windspeed)
	  ```
# After prefect, turning functions into tasks and making sure they retry and on intervals for success:
collapsed:: true
	-
	  ```python
	  import requests
	  
	  # Importing Prefect task, Flow and Python timdelta
	  from prefect import task, Flow
	  from datetime import timedelta
	  
	  # decorater specifying how many times to retry and it's iterval.
	  @task(max_retries=3, retry_delay=timedelta(minutes=3))
	  def extract() -> dict:
	      ...
	  
	  
	  @task
	  def transform(response: dict) -> float:
	      ...
	  
	  @task(max_retries=3, retry_delay=timedelta(5))
	  def load(speed: float):
	      ...
	  
	  
	  # Create a Prefect flow
	  with Flow("Windspeed Tracker") as flow:
	      # Execute tasks in the right order.
	      response = extract()
	      windspeed = transform(response)
	      load(windspeed)
	  
	  if __name__ == "__main__":
	      # Execute the flow
	      flow.run()
	  ```
-
  > The @task decorator converts a regular python function into a Prefect task. The optional arguments allow you to specify its retry behavior.
# Scheduling The Workflow
	-
	  ```python
	  # Imports to facilitate Scheduling.
	  from datetime import timedelta, datetime
	  from prefect.schedules import IntervalSchedule
	  
	  # Create a schedule object
	  schedule = IntervalSchedule(
	      start_date=datetime.utcnow() + timedelta(seconds=5),
	      interval=timedelta(minutes=1),
	  )
	  
	  # Attach the schedule object to the windspeed trakcer flow.
	  with Flow("Windspeed Tracker", schedule=schedule) as flow:
	      response = extract()
	      windspeed = transform(response)
	      load(windspeed)
	  ```
# UI Dashboard of your service
	- ![image.png](../assets/image_1629409912162_0.png)
	- To run this, you need to have docker and docker-compose installed on your computer. But starting it is surprisingly a single command.
	-
	  ```shell
	  prefect server start
	  ```
# Sending Emails
	- To send emails, we need to make the credentials accessible to the Prefect agent. You can do that by creating the below file in `$HOME/.prefect/config.toml`.
	-
	  ```toml
	  [context.secrets]
	  
	  EMAIL_USERNAME = "<Your email id>"
	  EMAIL_PASSWORD = "<your email password>"
	  ```
	-
	  ```python
	  # Import email task
	  from prefect.tasks.notifications.email_task import EmailTask
	  
	  # Create an email_task object. Use all static content here.
	  email_task = EmailTask(
	      subject="A new windspeed captured",
	      email_to="receiver_email@gmail.com",
	      email_from="your_email@gmail.com",
	  )
	  
	  with Flow("Windspeed Tracker", schedule=schedule) as flow:
	  
	      # Call the email task with variable content.
	      email_task(
	          msg=str(windspeed),
	      )
	  ```
-