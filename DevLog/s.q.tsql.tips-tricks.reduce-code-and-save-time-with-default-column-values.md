---
id: vpdkuqoibrgoveq2cbfd9m7
title: Reduce Code and save Time with Default Column Values
desc: ''
updated: 1646691264398
created: 1646691219629
---

> If you have a column that represents the datetime of when a record was loaded, there is no reason for you to write CURRENT_TIMESTAMP over and over when you insert data into that table.
> Instead, when you create the table, specify that column’s default value of GETDATE. You can do it programmatically or in the table designer.
> Below is an example of a data warehouse staging table template containing a primary key and standard audit columns. As you can see, each audit column has been assigned a default value there by reducing your insert statement by six lines.
> Considering you will be writing thousands of procs over your career, the time saved from not having to write six lines is significant.
>
> -- <https://tutorials.massstreet.net/v/transact-sql/solutions-to-real-world-problems/lesson-51.-reduce-code-and-save-time-with-default-column-values>

```sql
USE demo

CREATE TABLE YourSchemaName.YourStageTableName(
[ETLKey] [uniqueidentifier] NOT NULL,
[UniqueDims] [varbinary](35) NULL,
[UniqueRows] [varbinary](16) NULL,
[SourceSystem] [nvarchar](255) NULL,
[Cleansed] [bit] NULL,
[ErrorRecord] [bit] NULL,
[ErrorReason] [nvarchar](255) NULL,
[Processed] [bit] NULL,
[RunDate] [datetime] NULL,
 CONSTRAINT [PK_YourStageTableName] PRIMARY KEY CLUSTERED 
(
       [ETLKey] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]

GO

ALTER TABLE [YourSchemaName].[YourStageTableName] ADD  CONSTRAINT [DF_YourStageTableName_ETLKey]  DEFAULT (newid()) FOR [ETLKey]
GO
ALTER TABLE [YourSchemaName].[YourStageTableName] ADD  CONSTRAINT [DF_YourStageTableName_SourceSystem]  DEFAULT (N'Copia') FOR [SourceSystem]
GO
ALTER TABLE [YourSchemaName].[YourStageTableName] ADD  CONSTRAINT [DF_YourStageTableName_Cleansed]  DEFAULT ((0)) FOR [Cleansed]
GO
ALTER TABLE [YourSchemaName].[YourStageTableName] ADD  CONSTRAINT [DF_YourStageTableName_ErrorRecord]  DEFAULT ((0)) FOR [ErrorRecord]
GO
ALTER TABLE [YourSchemaName].[YourStageTableName] ADD  CONSTRAINT [DF_YourStageTableName_Processed]  DEFAULT ((0)) FOR [Processed]
GO
ALTER TABLE [YourSchemaName].[YourStageTableName] ADD  CONSTRAINT [DF_YourStageTableName_RunDate]  DEFAULT (getdate()) FOR [RunDate]
GO
```
