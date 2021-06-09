---
title: smtplib
tags: library
---

- [Article About Sending Emails](https://www.courier.com/blog/three-ways-to-send-emails-using-python-with-code-tutorials)
	-
	  > To create a secure connection, you can either use `SMTP_SSL()` with 465 port or `.starttls()` with 587 port. The former creates an SMTP connection that is secured from the beginning. The latter creates an unsecured SMTP connection that is encrypted via `.starttls()`.
	- To send email through `SMTP_SSL()`:
		-
		  ```python
		  import smtplib
		  
		  gmail_user = 'your_email@gmail.com'
		  gmail_password = 'your_password'
		  
		  sent_from = gmail_user
		  to = ['person_a@gmail.com', 'person_b@gmail.com']
		  subject = 'Lorem ipsum dolor sit amet'
		  body = 'consectetur adipiscing elit'
		  
		  email_text = """\
		  From: %s
		  To: %s
		  Subject: %s
		  
		  %s
		  """ % (sent_from, ", ".join(to), subject, body)
		  
		  try:
		      smtp_server = smtplib.SMTP_SSL('smtp.gmail.com', 465)
		      smtp_server.ehlo()
		      smtp_server.login(gmail_user, gmail_password)
		      smtp_server.sendmail(sent_from, to, email_text)
		      smtp_server.close()
		      print ("Email sent successfully!")
		  except Exception as ex:
		      print ("Something went wrong….",ex)
		  ```
	- To send email through `.starttls()`:
		-
		  ```python
		  
		  ```
-