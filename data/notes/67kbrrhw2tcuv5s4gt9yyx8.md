

## Sending Emails

- To send emails, we need to make the credentials accessible to the Prefect agent. You can do that by creating the below file in `$HOME/.prefect/config.toml`.

```toml
[context.secrets]

EMAIL_USERNAME = "<Your email id>"
EMAIL_PASSWORD = "<your email password>"
```

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
