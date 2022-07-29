
## Initial Setup Script

```bash
apt update
apt upgrade
# Makes it so i can add a repository for SQL Server to get installed later
apt install software-properties-common
```

## Install SQL Server

```bash
# Register the package
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
# Install SQL Server
sudo add-apt-repository "$(wget -qO- https://packages.microsoft.com/config/ubuntu/20.04/mssql-server-2019.list)"
sudo apt-get update
sudo apt-get install -y mssql-server
# Setup SA user with Password
sudo /opt/mssql/bin/mssql-conf setup
# 2 Developer Copy
# Yes to license agreement
# Password
# Verify Service is running
systemctl status mssql-server --no-pager
```

## Install SQL command line tools

```bash
sudo apt-get update 
sudo apt install curl
#Import the public repository GPG keys.
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
# Register the Microsoft Ubuntu repository.
curl https://packages.microsoft.com/config/ubuntu/20.04/prod.list | sudo tee /etc/apt/sources.list.d/msprod.list
# Update the sources list and run the installation command with the unixODBC developer package.
sudo apt-get update 
sudo apt-get install mssql-tools unixodbc-dev
# Add /opt/mssql-tools/bin/ to your PATH environment variable in a bash shell.
echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bash_profile
# To make sqlcmd/bcp accessible from the bash shell for interactive/non-login sessions, modify the PATH in the ~/.bashrc file with the following command:
echo 'export PATH="$PATH:/opt/mssql-tools/bin"' >> ~/.bashrc
source ~/.bashrc
```

## Enable SSH from external machines

- <https://pmsl.com.ng/ssh-into-a-proxmox-lxc-container/>

```bash
# in proxmox shell
lxc-attach --name 109
# change the line `PermitRootLogin` without-password to `PermitRootLogin` yes
vi /etc/ssh/sshd_config
# Restart the service
service ssh restart
```

## Enable the SQL Agent

```bash
sudo /opt/mssql/bin/mssql-conf set sqlagent.enabled true 
sudo systemctl restart mssql-server
```

## Set timezone

```bash
sudo timedatectl set-timezone America/Los_Angeles
```

## Setup ODBC Driver for connectivity to this server

- <https://manjaro.site/how-to-connect-to-microsoft-sql-server-using-python-on-macos-catalina/>

```bash
brew update
brew install unixodbc freetds # Install dependencies
sudo -H pip install pyodbc
tsql -C # Find freetds conf file
```

```bash
sudo nvim /usr/local/etc/freetds.conf # Add configuration information
```

```ini
[Ubuntu-Docker] # <-- Change this
host = 192.168.100.52 # <-- Change this
port = 1433
tds version = 7.3
```

```bash
tsql -S Ubuntu-Docker -U myUser -P myPassword # Test connection
```

```bash
odbcinst -j # Edit DSN files
```

```bash
sudo nvim /usr/etc/local/odbcinst.ini # Add configuration information
```

```ini
[FreeTDS]
DescriptionFreeTDS Driver for Linux MSSOL
Driver-/usr/local/lib/libtdsodbc.so
Setup-/usr/local/lib/libtdsodbc.so
UsageCount=1
```

```bash
sudo nvim /usr/etc/local/odbc.ini # Add configuration information
```

```ini
[Ubuntu-Docker]
Description = SOL Server on Ubuntu Docker
Driver = FreeTDS
Servername = Ubuntu-Docker
```

```bash
isql Ubuntu-Docker myUser myPassword # verify connectivity
```

### pyodbc connection to database

> Temporary issue with pyodbc <https://stackoverflow.com/questions/71067094/pyodbc-deprecation-warning-when-printing>
> work around: "set an environment variable named `PYTHONWARNINGS` to the value `ignore::DeprecationWarning` and then just run the script normally."

```python
import pyodbc
myconn = pyodbc.connect('DSN-Ubuntu-Docker;UID-sa;PWD=mYPasswd.23')
mycursor = myconn.cursor ()
myrows = mycursor.execute("SELECT @@VERSION").fetchall()
print(myrows)
mycursor.close()
myconn.close()
```
