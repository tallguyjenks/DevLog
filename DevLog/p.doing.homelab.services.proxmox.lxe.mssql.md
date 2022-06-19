---
id: p50tt2ssehdosmqr4wqug20
title: MSSQL
desc: ''
updated: 1655667602280
created: 1652558782274
---

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

## Setup ODBC Driver

```bash
if ! [[ "18.04 20.04 21.04" == *"$(lsb_release -rs)"* ]]; then
    echo "Ubuntu $(lsb_release -rs) is not currently supported." && exit;
fi
sudo su
curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add -
curl https://packages.microsoft.com/config/ubuntu/$(lsb_release -rs)/prod.list > /etc/apt/sources.list.d/mssql-release.list
sudo apt-get update
sudo ACCEPT_EULA=Y apt-get install -y msodbcsql18
sudo ACCEPT_EULA=Y apt-get install -y mssql-tools18 # optional: for bcp and sqlcmd
echo 'export PATH="$PATH:/opt/mssql-tools18/bin"' >> ~/.bashrc
source ~/.bashrc
sudo apt-get install -y unixodbc-dev # optional: for unixODBC development headers
```
