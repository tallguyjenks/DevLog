
## Process

To track WHO is changing things (basically the source control `Last Changed By` column) We needed a change log database

[Guide](https://documentation.red-gate.com/soc7/configuring/log-changes-to-shared-databases)

1. Running the following code to create the database

    ```sql
    USE master EXECUTE ('CREATE DATABASE ChangeLog')
    ALTER DATABASE ChangeLog SET ANSI_NULL_DEFAULT OFF
    ALTER DATABASE ChangeLog SET ANSI_NULLS OFF
    ALTER DATABASE ChangeLog SET ANSI_PADDING OFF
    ALTER DATABASE ChangeLog SET ANSI_WARNINGS OFF
    ALTER DATABASE ChangeLog SET ARITHABORT OFF
    ALTER DATABASE ChangeLog SET AUTO_CLOSE OFF
    ALTER DATABASE ChangeLog SET AUTO_CREATE_STATISTICS ON
    ALTER DATABASE ChangeLog SET AUTO_SHRINK OFF
    ALTER DATABASE ChangeLog SET AUTO_UPDATE_STATISTICS ON
    ALTER DATABASE ChangeLog SET READ_WRITE
    ALTER DATABASE ChangeLog SET RECOVERY SIMPLE
    ALTER DATABASE ChangeLog SET MULTI_USER
    ALTER DATABASE ChangeLog SET PAGE_VERIFY CHECKSUM
    ALTER DATABASE ChangeLog SET DB_CHAINING ON
    EXECUTE ('USE ChangeLog IF NOT EXISTS (SELECT * FROM sys.sysusers WHERE name=''guest'') EXECUTE sp_grantdbaccess guest')
    ```

2. - Close [[s.db.ms-sql-server.tools.ssms]]
3. - Navigate to `%localappdata%\Red Gate\SQL Source Control 7`
4. - Open `RedGate_SQLSourceControl_Engine_EngineOptions.xml` in a text editor
5. - Below the `EngineOptions version` line, add:
    1. - `<TraceCacheDatabase>ChangeLog</TraceCacheDatabase>`
    2. - **The above is case sensative**
6. - Save and close the file.

## Important Points

- Each developer **must** have `dbo_owner` permissions for the change log database.
- You can delete the change log database, **but history about changes will be permanently deleted**.
- SQL Source Control **will only use the change log database to save information about changes to linked databases**. It won't be used for any other purpose.
