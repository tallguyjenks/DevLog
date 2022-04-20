---
id: wjn7gyf9v25or1jci9x0asu
title: Link a Development Database to Your Source Control System
desc: ''
updated: 1649361275424
created: 1649361275424
---

## [Linking a development database to your source control system][2]

- Can link your database to a repository solution
  - Right click on database
  - link database with source control
  - link to my source control system
  - Select your source control **which for ADO? git?**
    - Browse for target folder
    - Click on it
    - Add commit Message
    - OK
    - select either (See [[#shared-vs-dedicated-development-model]])
      - dedicated database
      - shared database
  - When link is complete the DB icon will turn green
  - You need to start by committing all your objects
  - Click on "Commit" in Redgate source control
  - add commit message
  - Commit
    - this will export all your objects as create scripts to your source control

[2]: https://www.red-gate.com/hub/university/courses/sql-source-control/sql-source-control/getting-started/linking-development-database-source-control-system
