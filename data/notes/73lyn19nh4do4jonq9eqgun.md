

| Port number    | Type        | Use                                                                |
|----------------|-------------|--------------------------------------------------------------------|
| 135            | TCP         | WMI, MSDTC, Agent file copy, T-SQL debugging                       |
| [[n.port.80]]             | TCP         | To publish SQL Server Reporting Services (SSRS) reports using HTTP |
| [[n.port.443]]           | TCP         | To publish SSRS reports using HTTPS                                |
| 500            | UDP         | IPSec to encrypt connections                                       |
| 1024 to 5000   | TCP         | Dynamic ports for named instances                                  |
| [[n.port.1433]]          | TCP         | Database engine default instance                                   |
| 1434           | TCP and UDP | DAC and the SQL Browse                                             |
| 2382           | UDP         | SQL Server Analysis Services with dynamic ports                    |
| 2383           | TCP         | SQL Server Analysis Services (SSAS)                                |
| 2725           | TCP         | SQL Server Analysis Services (SSAS)                                |
| 3343           | UDP         | Cluster network driver                                             |
| 3882           | TCP         | SQL Server Integration Services (SSIS)                             |
| 4022           | TCP         | SQL Broker Service                                                 |
| 4500           | UDP         | IPSec                                                              |
| 5000 to 5099   | UDP         | Clusters                                                           |
| 5022           | TCP         | AlwaysOn                                                           |
| 7022           | TCP         | Database Mirroring                                                 |
| 8011 to 8031   | UDP         | Cluster internode                                                  |
| 49152 to 65535 | TCP         | More dynamic ports for named instances                             |
