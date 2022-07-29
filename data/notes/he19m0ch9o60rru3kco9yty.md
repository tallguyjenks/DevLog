

- `Author:` Robby Boney
- `Link:` <https://medium.com/short-bits/an-extremely-simple-way-to-schedule-programs-with-python-on-windows-46fc34074874>
- `Publish Date:` 2021.12.14
- `Reviewed Date:` [[log.daily.2021.12.20]]

---

- [[s.l.python.libs.schedule]] library:


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
- Schedule a python script on windows with a 3 file setup
  - A bat file which can be executed (directly or via shortcut) automatically by windows in the startup folder
    - ![alt](assets/images/Pasted_image_20211220105600.png)
    - Ensure this runs even after an automatic or scheduled restart by placing the script or a shortcut to it in the startup directory which can be found by running:
      - `shell:startup` in the menu that pops up when you press <kbd>ctrl</kbd>+ <kbd>R</kbd>
  - a manager powershell script to perform any setup steps like activating a conda environment and then running the scheduler
    - ![alt](assets/images/Pasted_image_20211220105611.png)
  - a scheduler python script that runs a python function or command line script via a package like `subprocess`
    - ![alt](assets/images/Pasted_image_20211220105625.png)

## When Does this NOT Work

- schedule is designed as a simple scheduling package. As mentioned on the the projects documentation, it is not ideal when the following are required:
  - **Job persistence** (remember schedule between restarts) (although we have “somewhat” solved this one in this article)
  - **Exact timing** (sub-second precision execution)
  - **Concurrent execution** (multiple threads)
  - **Localization** (time zones, workdays or holidays)

