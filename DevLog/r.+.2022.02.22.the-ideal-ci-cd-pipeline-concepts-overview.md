---
id: m5cPigrU8Ryj9dBfXcRdR
title: The Ideal CI CD Pipeline Concepts Overview
desc: ''
updated: 1645579800227
created: 1645579199516
---

<https://youtu.be/OPwU3UWCxhw>

- **Source** ([[cli.cmd.git]])
- **Build**
  - Should be Toggle-able for when you dont want something to run through the gamut
  - Compile Source and Dependencies
  - Unit tests
  - Coverage > 90%
- **Test**
  - Should be Toggle-able for when you dont want something to run through the gamut
  - Integration tests
    - If you have an [[terms.api]] then test a POST request followed by a GET request
    - If you have external service dependencies, test them too
    - In essence, test the core functionality of your app so that changed behavior will easily show up
- **Prod** Environment
  - 1 Box (have incremental roll out to a single machine or a small fraction of them so impacts are smaller and more readily identified and rolled back)
  - Alarms on Errors, Latency, and Key business Metrics can indicate a needed rollback
    - Robust system can monitor these and run an automated rollback
  - Bake Period (24hrs)
    - Testing that the change is still good live in prod
    - Anomaly Detection or Error counts + Latency Breaches over the time period
  - Canary (in a coal mine)
    - Have a cron job test the [[terms.api]] at a regular interval (POST/GET/UPDATE/DELETE etc.)
    - Should the cron job fail then it can be an alarm.
