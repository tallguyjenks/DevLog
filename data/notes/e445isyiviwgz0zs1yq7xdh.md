

<center><iframe width="560" height="315" src="https://www.youtube.com/embed/OPwU3UWCxhw" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></center>

![Ideal Pipeline](/assets/images/2022-02-22-17-35-55.png)

- **Source** 
  - [[cli.cmd.git]] version control
  - Require `X` reviewers
  - Independent Dev DB and any dependencies are replicated for Dev copies
- **Build**
  - Should be Toggle-able for when you dont want something to run through the gamut
  - Compile Source and Dependencies
  - Unit tests
  - Coverage > 90%
- **Test**
  - Independent Test DB
  - Should be Toggle-able for when you dont want something to run through the gamut
  - Integration tests
    - If you have an [[terms.api]] then test a POST request followed by a GET request
    - If you have external service dependencies, test them too
    - In essence, test the core functionality of your app so that changed behavior will easily show up
- **Prod** (1box)
  - Independent Prod DB
  - 1 Box (have incremental roll out to a single machine or a small fraction of them so impacts are smaller and more readily identified and rolled back)
  - Alarms on Errors, Latency, and Key business Metrics can indicate a needed rollback
    - Robust system can monitor these and run an automated rollback
  - Bake Period (24hrs)
    - Testing that the change is still good live in prod
    - Anomaly Detection or Error counts + Latency Breaches over the time period
  - Canary (in a coal mine)
    - Have a cron job test the [[terms.api]] at a regular interval (POST/GET/UPDATE/DELETE etc.)
    - Should the cron job fail then it can be an alarm.
- **Prod**
  - The other 90% of the traffic
  - Also has all the Alarms, canary, etc. from the 1box too
  - Traffic split through [[n.protocol.dns]]?
