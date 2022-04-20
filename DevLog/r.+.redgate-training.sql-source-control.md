---
id: 2ey5t71gyev0bdfxpduqw22
title: Sql Source Control
desc: ''
updated: 1649713268282
created: 1649713268282
---

### Getting Started with SQL Source Control

#### Getting Started

##### [Linking a development database to your source control system](https://www.red-gate.com/hub/university/courses/sql-source-control/sql-source-control/getting-started/linking-development-database-source-control-system)

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

##### [Shared vs Dedicated development model][3]

- Shared is redundant when it comes to "pull changes" because everyone shares the same DB and changes are pushed to the repository
- Dedicated is like the standard git model where all devs have their own copy of changes but to actually implement those changes they have to commit the changes to source control
  - and by effect move through the PR processgg

##### [Alternative linking options][]

- `Just let me try it out`: Great way to test the tool or show the team

##### Linking static data tables

1. Right click a database in [[s.q.tsql.tools.ssms]]
2. `Other SQL Source Control tasks`
3. `Link or unlink static data`
4. `save and close`
5. Right click a database in [[s.q.tsql.tools.ssms]]
6. `Commit changes to source control`
7. In source control pane you will now see a commit with the data link change type that shows the diff as a bunch of insert statements
8. Commit message and commit
   - Result is that in your source control repository there is now a `Data/` directory with a SQL file in it consisting of the insert statements.

- **To source control the data on your tables they need a PK**

#### Working with SQL Source Control

##### Committing changes

- any changes made to DB ojects just
  - Right click a database in [[s.q.tsql.tools.ssms]]
  - `Commit changes to source control`

##### Sharing changes with a team using SQL Source Control

- New database exists

1. Right click a database in [[s.q.tsql.tools.ssms]]
2. `Link this database to source control`
3. Instead of committing, `get latest` to `git pull` your team's work into your now versioned DB

##### Working with Distributed Version Control Systems

- If using git then you need to commit changes to the local repository first (the folder on your local machine)
- Then SQL Source Control will tell you that there is a commit in your local repository that can be pushed to the remote repository and give you an easy button to do that.

##### Reviewing the history

- Right click on the object in the [[s.db.ms-sql-server.tools.ssms]] object explorer
- `View History`
- see the commit history of an object

##### Undoing a change

1. Right click a database in [[s.q.tsql.tools.ssms]]
2. `Other SQL Source Control Tasks`
3. `Undo Changes`

Rolling back changes (undo) on the database to a prior state:

1. Right click a database in [[s.q.tsql.tools.ssms]]
2. `View History`
3. left click on version line item you want to roll back to
4. At bottom of menu `Update your database to the selected version using:`
   - Select your compare product to do the comparison

#### Advanced SQL Source Control operations

##### Conflict resolution

##### Using object locking with SQL Source Control

- For shared database model (think sharepoint item checkout)

##### Setting up filters

- Filter rules are basically a GUI version of a gitignore for ignoring certain types of objects

##### Updating to a previous revision

#### Manual Deployments with SQL Source Control

##### Deploying schema changes with SQL Compare

##### Deploying data changes with SQL Data Compare

##### Deploying without access to your target
