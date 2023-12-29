# Perform-a-SQL-Query

<h2>Activity overview</h2>

  Previously, I learned how to use basic SQL queries to retrieve information from a database. I have also learned about using the ```ORDER BY``` keyword to sort data returned in an ascending or descending order.

In this lab activity, I’ll use ```SELECT``` and ```FROM``` in SQL to return the information I need from a database. I’ll also use the ```ORDER BY``` keyword to sequence the information returned by a query based on a specified column.

It's important to know how to query information from a database because this is a common task I might encounter as a security analyst. I should know how to get the information I need to improve security and keep data safe.

Note: The terms row and record are used interchangeably in this lab activity.

<h2>Scenario</h2>

In this scenario, I have to determine which employee devices must be updated. I also need to investigate user login activity to explore if any unusual activity has occurred.

The information I need is located in the ```machines``` and ```login_attempts``` tables in the ```organization``` database.

Here’s how I’ll do this task: First, I’ll obtain information on the employee devices that must be updated. Next, I’ll examine the login attempts for unusual activity. Finally, I’ll use the ```ORDER BY``` keyword to sort the data returned by my SQL queries.

<h2>Task 1. Retrieve employee device data</h2>

In this task, I need to obtain information on employee devices because my team needs to update them. The information I need is in the ```machines``` table in the ```organization``` database.

First, I need to retrieve all the information about the employee devices.

1. Run the following query to select all device information from the ```machines``` table:

```SELECT *```

```FROM machines;```

Note: Using the asterisk (*) returns all data from the specified table. Also, table names in MySQL are case-sensitive.
The output returns all the contents of the machines table:

![image](https://github.com/n8som/Perform-a-SQL-Query/assets/110139109/d3dbb950-f52d-4241-9c60-a97bf371fb09)

Next, I want to focus on the email client running on various devices.

2. Run the following query to select only the ```device_id``` and ```email_client``` columns from the ```machines``` table. Replace ```X``` with ```device_id``` and ```Y``` with ```email_client```:

```SELECT X, Y FROM machines;```

Here, I see email client 2 is returned in the third row:

![image](https://github.com/n8som/Perform-a-SQL-Query/assets/110139109/7686a32a-688f-4abd-93c6-4d3d9dd4c357)

Now, I need information on the operating systems used on various devices and their last patch date.

3. Complete the query to return only the ```device_id```, ```operating_system```, and ```OS_patch_date``` columns from the ```machines``` table. Replace X, Y, and Z with the columns that I need to return:

```“SELECT X, Y, Z FROM machines;”```

Here I see 2021-09-01 is the patch date of the first entry:

![image](https://github.com/n8som/Perform-a-SQL-Query/assets/110139109/714577cf-7871-4345-9de7-50c98bff275c)

<h2>Task 2. Investigate login activity</h2>

In this task, I need to analyze the information from the ```log_in_attempts``` table to determine if any unusual activity has occurred.

First, I need to investigate the locations where login attempts were made to ensure that they’re in expected areas (the United States, Canada, or Mexico).

1. Write a SQL query to select the ```event_id``` and ```country``` columns from the ```log_in_attempts``` table.

Here I see there were no login attempts from Australia:

![image](https://github.com/n8som/Perform-a-SQL-Query/assets/110139109/61d2b9b8-7bdf-4438-a8ae-28e1f9013156)

Next, I need to check if login attempts were made outside of the organization's working hours.

2. Write a SQL query that selects the ```username```, ```login_date```, and ```login_time``` columns from the ```log_in_attempts``` table.

Here I see the username, jrafael, returned in the fifth row:

![image](https://github.com/n8som/Perform-a-SQL-Query/assets/110139109/b7957818-6a0f-41f9-91aa-28108e73c2d0)

Now, I need to get a complete picture of all login attempts.

3. Write a SQL query that selects all columns from the ```log_in_attempts``` table, using a single symbol after the ```SELECT``` keyword.

![image](https://github.com/n8som/Perform-a-SQL-Query/assets/110139109/44101b5a-7078-4d4f-b17d-fadc6144447e)

<h2>Task 3. Order login attempts data</h2>

In this task, I need to use the ```ORDER BY``` keyword. I'll sequence the data that my query returns according to the login date and time.

First, I need to sort the information by date.

1. Run the following query, which orders ```log_in_attempts``` data by ```login_date```:

```SELECT *```

```FROM log_in_attempts```

```ORDER BY login_date;```

Here I see the username and login date, ivelasco on 2022-05-08, for the first record returned:

![image](https://github.com/n8som/Perform-a-SQL-Query/assets/110139109/f0b6d00d-ab7f-4fef-affd-284c964a17e4)

Now, I need to further organize the previous results by ordering them by ```login_time```.

2. Modify the query from the previous step by adding the login time to the ```ORDER BY``` clause. I must replace X with the appropriate column name:

```“SELECT *```

```FROM log_in_attempts```

```ORDER BY login_date, X;”```

Here I see bsand at 00:19:11 is the first record returned from the above query:

![image](https://github.com/n8som/Perform-a-SQL-Query/assets/110139109/bde4d6db-1fab-426c-b5bb-358d2a41e602)

<h2>Conclusion</h2>

I now have practical experience in running basic SQL queries to

- select specific columns from a table,
- select all columns from a table by using an asterisk (*), and
- sort query results using the ORDER BY keyword.

These basic queries form the foundation for running more advanced queries and applying filters later.

