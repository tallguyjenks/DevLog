

```python
import schedule
import time

def job():
  print("I'm working...")
schedule.every(10).seconds.do(job)
schedule.every(10).minutes.do(job)
schedule.every().hour.do(job)
schedule.every().day.at("10:30").do(job)
schedule.every(5).to(10).minutes.do(job)
schedule.every().monday.do(job)
schedule.every().wednesday.at("13:15").do(job)
schedule.every().minute.at(":17").do(job)
while True:
  schedule.run_pending()
  time.sleep(1)
```

- The package includes many other actions available from the main API including:
  - Use a decorator to schedule a job
  - Pass arguments to a job schedule.every(2).seconds.do(greet, name="Alice")
  - Cancel a job
  - Run a job once
  - Get all jobs
  - Cancel all jobs
  - Get several jobs, filtered by tags
  - Cancel several jobs, filtered by tags
  - Run a job at random intervals
  - Run a job until a certain time
  - Time until the next execution
  - Run all jobs now, regardless of their scheduling

- Reference:
  - [[r.(.2021.12.20.an-extremely-simple-way-to-schedule-programs-with-python-on-windows]]
