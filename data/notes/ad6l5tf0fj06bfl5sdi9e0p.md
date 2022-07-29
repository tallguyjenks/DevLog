

## Before ETL Process:

```python
import requests

def extract() -> dict:
  """Use the Open Weather Map API to fetch Boston weather data.
  Returns:
	  dict: a JSON response of many wheather measurements.
  """

  url = "https://api.openweathermap.org/data/2.5/weather"

  #  Use a real API key. You can get a free one from https://openweathermap.org/
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

## After prefect, turning functions into tasks and making sure they retry and on intervals for success:

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
