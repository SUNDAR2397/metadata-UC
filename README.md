Defines the base path for the files stored in ABFS.
Lists files in the specified directory using dbutils.fs.ls.
Filters the files based on the specified pattern.
Checks if the metadata table exists in the specified Unity Catalog schema and creates it if necessary.
Processes each file that hasn't been successfully processed according to the metadata table, updates the table with the processing status, and handles any exceptions that may occur.


table('ADFActivityRun')
| where ErrorCode contains "File Not Found"
| where Status contains "failed"
| where ErrorMessage contains "Please"
| project ErrorCode, ErrorMessage
