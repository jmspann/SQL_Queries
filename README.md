<h1>SQL Queries</h1>

<h2>Description</h2>
In this lab, we will query SQL databases to access specific information contained within them. We will utilize the <em><strong>SELECT</strong></em>, <em><strong>FROM</strong></em> and <em><strong>ORDER BY</strong></em> commands. We will also practice joining tables in SQL to return data contained within one or both tables. SQL will be accessed through the Linux command line by typing the command <em><strong>sqlite3</strong></em> in the command line.
<br />


<h2>Languages and Utilities Used</h2>

- <b>SQL</b>

<h2>Environments Used </h2>

- <b>SQL</b>
- <b>Linux Bash Shell</b>

<h2>Program Walk-Through:</h2>

<h3>SQL Querying</h3>

<p align="center">
We need to obtain information on employee devices so our team can update them. This information is located in the "machines" table in the "organization" database. We can access it by using the <em><strong>SELECT</strong></em> and <em><strong>FROM</strong></em> commands: <br/>
<img src="https://i.imgur.com/LMEUEp1.png" height="100%" width="100%" alt="SQL Query"/>
<br />
<br />
We only want to focus on the "device_id" and "email_client" columns from the table:  <br/>
<img src="https://i.imgur.com/ConnInx.png" height="100%" width="100%" alt="SQL Query"/>
<br />
<br />
Now we only want to return the "device_id", "operating_system", and "OS_patch_date" columns from the table: <br/>
<img src="https://i.imgur.com/IZYQoRF.png" height="100%" width="100%" alt="SQL Query"/>
<br />
<br />
Next, we need to analyze information from the "log_in_attempts" table for any unusual activity. We'll first investigate if any login attempts were outside of the expected areas (US, Canada, and Mexico) by pulling the "event_id" and "country" columns:  <br/>
<img src="https://i.imgur.com/cXgSk9C.png" height="100%" width="100%" alt="SQL Query"/>
<br />
<br />
Next, we'll check if any login attempts were made outside of working hours. We'll first pull the "username", "login_date", and "login_time" columns, followed by selecting all of the columns to get a whole picture of login attempt hours: <br/>
<img src="https://i.imgur.com/TRqUqUi.png" height="100%" width="100%" alt="SQL Query"/> <br/>
<br />
<img src="https://i.imgur.com/0zHFiLK.png" height="100%" width="100%" alt="SQL Query"/>
<br />
<br />
Now we will sequence the data according to the login date and time using the <em><strong>ORDER BY</strong></em> command: <br/>
<img src="https://i.imgur.com/KGwhkAN.png" height="100%" width="100%" alt="SQL Query"/>
</p>
<br />
<br />

<h3>SQL Joins</h3>

<p align="center">
We need to identify which employees are using which machines. The data is located in the "machines" and "employees" tables. To access this, we will query the "machines" table and perform a join between it and the "employees" table using an <em><strong>INNER JOIN</strong></em> on their shared column "device_id":  <br/>
<img src="https://i.imgur.com/CydFVYS.png" height="100%" width="100%" alt="SQL Joining"/>
<br />
<br />
Now we must return information on all machines and the employees who have them by using <em><strong>LEFT JOIN</strong></em> to include all data from the first mentioned "machines" table. This query will also include any machines that are not assigned to an employee:  <br/>
<img src="https://i.imgur.com/jzUnF2N.png" height="100%" width="100%" alt="SQL Joining"/>
<br />
<br />
Next, we must return information of all employees and any machines that are assigned to them by using <em><strong>RIGHT JOIN</strong></em>, which includes all data from the second mentioned "employees" table. This includes any employees who may not have any machines assigned to them:  <br/>
<img src="https://i.imgur.com/rmjIa5T.png" height="100%" width="100%" alt="SQL Joining"/>
<br />
<br />
Finally, we need to retrieve the information on all employees who have made login attempts by performing an <em><strong>INNER JOIN</strong></em> and linking them on their common "username" column:  <br/>
<img src="https://i.imgur.com/fpPJKy1.png" height="100%" width="100%" alt="SQL Joining"/>
</p>
<br />
<br />


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
