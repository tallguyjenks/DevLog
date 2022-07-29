

> The @task decorator converts a regular python function into a Prefect task. The optional arguments allow you to specify its retry behavior.

## Scheduling The Workflow

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
