

Reference: <https://severalnines.com/database-blog/overview-job-scheduling-tools-postgresql>

Like [[s.q.tsql.tools.sql-agent]] it is a job scheduling agent available for PostgreSQL that allows the execution of stored procedures, SQL statements, and shell scripts.

The purpose is to have this agent running as a daemon on Linux systems and periodically does a connection to the database to check if there are any jobs to execute.

This scheduling is easily managed by PgAdmin 4, but it’s not installed by default once the pgAdmin installed, it’s necessary to download and install it on your own.
