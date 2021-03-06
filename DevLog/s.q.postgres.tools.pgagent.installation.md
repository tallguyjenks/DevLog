---
id: ytr0zhk9rwilnv9u1mjzpvc
title: Installation
desc: ''
updated: 1642232683598
created: 1642232485297
---


## Step 1

Installation of pgAdmin 4

```bash
sudo apt install pgadmin4 pgadmin4-apache
```

## Step 2

Creation of plpgsql procedural language if not defined

```sql
CREATE TRUSTED PROCEDURAL LANGUAGE 'plpgsql'
HANDLER plpgsql_call_ handler
HANDLER plpgsql validator;
```

## Step 3

Installation of pgAgent

```bash
sudo apt-get install pgagent
```

## Step 4

Creation of the pgagent extension

```sql
CREATE EXTENSION pageant
```

In order to define a new job, it's only necessary select "Create" using the right
button on "pgAgent Jobs", and it'll insert a designation for this job and define the
steps to execute it:

![pgagent](/assets/images/2022-01-14-23-43-37.png)

![job](/assets/images/2022-01-14-23-44-04.png)

![schedules](/assets/images/2022-01-14-23-44-19.png)

## Step 5

Finally, to have the agent running in the background it's necessary to launch the
following process manually:

```bash
/usr/bin/pgagent host=localhost dbname=postgres user=postgres port=5432 -l 1
```

