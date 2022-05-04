---
id: faytj94ihnr194nopiw4lzj
title: Workflow
desc: ''
updated: 1651013750263
created: 1649361469294
---

## Deploying New DB from TEST to PROD

1. Create same name copy of DB onto PROD
2. Link that DB with the working folder you've been working out of
3. `Get Latest`
4. Apply changes
   - If there are changes on the remote Repository you can pull those too to apply those changes as well

## Every Day Workflow

- This assumes all setup and connection work has been done for redgate work
- The following examples assume you're performing all this work on 1 SQL Server: `TEST` and that downstream, migration scripts will be applied to push those changes automatically onto the `PROD` server without human intervention.

### Getting Started and Setup

- Main repository is Repo @ `PROD`
  - They pull the repo and branch down to local machine
  - People make their own branch off of `PROD` that will contains the changes they want for specific work
  - they are now up to date and ready to work
- Cloning the database you want to work in
  <!-- - Right click the database you want to change
  - `Tasks > Copy Database` -->
- Open [[s.q.tsql.tools.redgate.products.sql-compare]]
  - Select Source Server and Database
  - Select Target Server and in the database selection dropdown type the name of your new DEV copy of the database
    - The new empty database naming convention being DATABASE_BSJ_DEV
    - the database name in all caps, followed by the developers initials, and ended with DEV so people know its someones development copy
    - When the name is ready click the `Create` link below the dropdown
  - Continue through the Sql Compare menus and no need to save or backup the migration scripts
  - After copying of the database is complete you're ready to begin work if changes are only schema related
    - Right click that new DB and `Link with source control`
    - `Link with my source control system`
    - Select the folder location of the database from within the repository
    - `Get Latest` if applicable
    - `Apply Changes` if applicable
    - Developer is now free to make changes to schema, objects, etc inside their test database
- If data is also required within the dev copy from the source database then open [[s.q.tsql.tools.redgate.products.data-compare]]
  - Select Source Server and Database
  - Select Target Server and in the database selection dropdown type the name of your new DEV copy of the database you made prior
  - No need to save the migration scripts and run everything within the Data Compare tool for deployment
  - Select the data to copy across databases
  - `Deploy`
  - Now your schema and data all match across the servers and databases
    - Right click that new DB and `Link with source control`
    - `Link with my source control system`
    - Select the folder location of the database from within the repository
    - `Get Latest` if applicable
    - `Apply Changes` if applicable
    - Developer is now free to make changes to schema, objects, etc inside their test database

### Getting your change into the Pull Request process

- Make your changes, New UDF, new USP, modify existing items, make new tables, alter other tables, etc.
- When ready, or incrementally throughout the process add your changes to your branch via commits
- when you are ready to enter the PR process push your branch to the remote repository
- open pull request of your branch into the master branch
- Normal PR process occurs here
- Once PR is merged then at that point CI/CD pipelines should take over to build, test, and deploy the changes to the `PROD` server with no human intervention.
  - **IF NO AUTOMATED PROCESS YET PROCEED TO SECTION BELOW**

#### Manual implementation of new changes in the absence of a CI/CD pipeline

<!-- - Back in [[s.db.ms-sql-server.tools.ssms]] select your target database (the one you wanted to make changes to not your DEV copy of it)
- Got to the SQL Source Control Interface and `Get Latest`
- Apply Changes -->
- Open [[r.+.redgate-training.sql-change-automation]]
- Pick your source and target for changes
  - Based on this proposed workflow your source would be the "master" copy of the Database on the `TEST` server
  - Based on this proposed workflow your target would be the same Database on the `PROD` server
- Select desired changes to be implemented
- Click `Deploy` to generate a migration script to implement changes without modification to the repository code
  - If the individual cannot run the code then pass it to someone who can as a final deliverable artifact to be executed and discarded
