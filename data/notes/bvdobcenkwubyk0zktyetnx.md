
## Linking static data tables

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
