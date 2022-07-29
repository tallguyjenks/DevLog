
Spent most of the morning finishing up all my report views for the financial transactions, then moved on to how to get flat file data into the server. turns out SQL Server hosted on linux cannot use the `bulkadmin` role and bulk insert is basically out the window or if its not the configuration for it was a mire of unhelpful articles so i went for the custom python/pandas insert route

enter database driver issues. since im not on windows at all i cant use the `ODBC Driver 17 for SQL Server` driver that we use adnauseum at work i had to figure out a bunch of round about crap to get a driver so i could connect to my server container running on the hypervisor. finally got that figured out now im just designing process around how to deal with the files so my partner and i can manage our transactions easier.

thinking something like:

- she gets a custom drop off point in her file share on the NAS
- python file watch sees new file
- python copies file to sql server private share
- python processes the file and upserts data and metrics
- python adds file name to list of file names to ignore because it was been processed already
- python uses sql server to send my partner a text that her file was processed successfully

✨ D A T A ✨
