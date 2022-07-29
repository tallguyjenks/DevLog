
## Link

<https://www.windowscentral.com/how-create-task-using-task-scheduler-command-prompt>

## Notes

CLI way to schedule tasks akin to Task Scheduler functionality

### Syntax

For more info

```powershell
SCHTASKS /CREATE /?
SCHTASKS /CHANGE /?
SCHTASKS /DELETE /?
```

---

```powershell
SCHTASKS /CREATE /SC DAILY /TN "FOLDERPATH\TASKNAME" /TR "C:\SOURCE\FOLDER\APP-OR-SCRIPT" /ST HH:MM
```

- `/CREATE` — specifies that you want to create a new an automated routine.
- `/SC` — defines the schedule for the task. Options available, include MINUTE, HOURLY, DAILY, WEEKLY, MONTHLY, ONCE, ONSTART, ONLOGON, ONIDLE, and ONEVENT.
- `/D` — specifies the day of the week to execute the task. Options available, include MON, TUE, WED, THU, FRI, SAT, and SUN. If you're using the MONTHLY option, then you can use 1 - 31 for the days of the month. Also, there's the wildcard "*" that specifies all days.
- `/TN` — specifies the task name and location. The "MyTasks\Notepad task" uses the "Notepad task" as the name and stores the task in the "MyTasks" folder. If the folder isn't available, it'll be created automatically.
- `/TR` — specifies the location and the name of the task that you want to run. You can select an app or custom script.
- `/ST` — defines the time to run the task (in 24 hours format).
- `/QUERY` — displays all the system tasks.
- `/RU` — specifies the task to run under a specific user account.

### Example

#### Create Task

```powershell
SCHTASKS /CREATE /SC DAILY /TN "MyTasks\Notepad task" /TR "C:\Windows\System32\notepad.exe" /ST 17:45
```

![created task](/assets/images/2022-03-03-17-45-22.png)

#### Change Task

- `/CHANGE` — specifies that you want to edit an existing task.
- `/TN` — specifies the name and location of the task that you want to modify.
- `/ST` — defines the new time to run the automated routine.
- `/DISABLE` — disables the task.

```powershell
SCHTASKS /CHANGE /TN "MyTasks\Notepad task" /ST 09:00
```

#### Disable a Task

And the inverse of this is just replace `/DISABLE` with `/ENABLE`

```powershell
SCHTASKS /CHANGE /TN "FOLDERPATH\TASKNAME" /DISABLE
```

#### Delete Task

- `/DELETE` — specifies that you want to delete an existing task.
- `/TN` — specifies the name and location of the task that you want to delete.

```powershell
SCHTASKS /DELETE /TN "MyTasks\Notepad task"
```
