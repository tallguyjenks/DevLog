
1. Make Empty Git repository on Azure DevOps
2. Make sure git repo has a master branch on the remote
   - If you cannot make this happen, it can be fixed later and might just have to be
3. Setup [[s.q.tsql.tools.redgate.implementation.changelog-database]]
   - Or at least make sure all users have followed steps to get added to changelog DB
4. if no remote master branch then errors will occur in the local repository
   - To correct errors of missing `origin/master` run `git branch --unset-upstream` since an upstream `master` branch doesn't yet exist
   - This will arise when you add a DB to the source control and try to enter the commit screen
5. Make a new folder for each Version Controlled DB in your Repo
   - Convention being used is to name each folder the same as the DB's name but in all CAPS
6. Setup Source control filters so you essentially have gitignore functionality in the repository
7. [[s.q.tsql.tools.redgate.implementation.link-a-development-database-to-your-source-control-system]]
   - If applicable [[s.q.tsql.tools.redgate.implementation.linking-static-data]]
