# Data 301 - Lab 4
## Setup
Follow the steps to get ready for lab 4!
> Since I'm using a mac the following steps are experimented based on Macos.

1. Download the latest version of [Mysql](https://www.mysql.com).
2. Install it properly and add it to the environment variable.
    - MacOS (Ventura 13.1): add `export PATH=${PATH}:/usr/local/mysql-8.1.0-macos13-x86_64/bin` to your `.bash_profile` under home directory.
3. Start the Mysql server
4. Open a new terminal and run `mysql -u root -p`, then enter your password.
5. Create a new database called `mydb` with the following code:
```mysql=
mysql> CREATE DATABASE mydb;

mysql> USE mydb;
```

- [Download Mysql on Windows](https://www.youtube.com/watch?v=2om3byn2lxs)
- [Download Mysql on MacOS](https://www.youtube.com/watch?v=2cvH0HRjZF8)


## Create
Create a table with the following information:
- Table name: `vendor` 
- Fields:
    1. `id` with data type integer that is the key
    2. `name` with data type holding up to 50 characters
    3. `address` with data type holding up to 60 characters
    4. `state` with data type holding exactly 2 characters
    5. `upcprefix` with data type holding exactly 5 characters
    6. `balance` with data type that can hold a currency (money field with up to 10 total digits and 2 decimal places) 
    7. `createddate` with data type that is a date
> Use `DESCRIBE vendor;` to double check your work.


```
# code here
CREATE TABLE vendor (
    id          INT PRIMARY KEY,
    name        VARCHAR(50),
    address     VARCHAR(60),
    state       CHAR(2),
    upcprefix   CHAR(5),
    balance       DECIMAL(10,2),
    createdate  DATE
);
```

## Insert
Insert the following rows into the `vendor` table:
1. (1, 'UBC Cookie Company', '3333 University Way', 'BC', '00001', 955463.77, '2016-01-02')
2. (2, 'Salerno Foods', '123 5th Street', 'MA', '14700', 150000.00, '2016-01-04')
3. (3, 'Keebler Company', 'Battle Creek', 'MI', '30100', 255000.00, '2016-01-08')
4. (4, 'Good Bakery', '45 Freedom Road', 'TX', '38281', 123472.99, '2016-01-23')
5. (5, 'Nabisco', 'East Hanover', 'NJ', '44000', 0, '2016-01-11')
6. (6, 'Matt's Cookies', '482 North Milwaukee Avenue', 'IL', '79746', 999.99, '2016-01-15')

```
# code here

```
- [INSERT statement](https://www.w3schools.com/mysql/mysql_insert.asp)


## Update
Write the following `UPDATE` statements:
1. Update all `vendor` `balances` to increase them by 28%.
2. Update the `vendor` `name` to 'Cookie Company', created `createdate` to '2016-01-25', and `state` to 'CA' for `vendor` with `id` = 1.

```
# code here

```
- [Update statement](https://www.w3schools.com/mysql/mysql_update.asp)


## Delete
Write the following `DELETE` statements:
1. Delete all vendors in the `state` 'IL'.
2. Delete vendor with `id` = 1.

```
# code here

```
- [Delete statement](https://www.w3schools.com/mysql/mysql_delete.asp)

+----------------------------------------------------------------------------+
| **Now load the `lab4.sql`** into your database.                            |
|                                                                            |
|```                                                                         | 
| mysql> source <path_to>/lab4.sql                                           |
|                                                                            |
| ```                                                                        |
| - `show tables;`: to check if table is successfully created.               |
| - `drop table sales;`: to erase everything if made any mistakes.           |
+----------------------------------------------------------------------------+

## Query
1. [Table **sales**] Return the sales records (all fields) for store 12 where the move is less than 30. Limit the result to show only the first 5 rows. 
- [Select statement](https://www.w3schools.com/mysql/mysql_select.asp)
- [Limit statement](https://www.w3schools.com/mysql/mysql_limit.asp)

```
# code here

```


2. [Table **vendor**] Return the vendor name, address, and balance for vendors created between January 3, 2016 and March 3, 2016. Sort rows by balance ascending.
- [Between statement](https://www.w3schools.com/mysql/mysql_between.asp)
- [Order by statement](https://www.w3schools.com/mysql/mysql_orderby.asp)

```
# code here

```


3. [Table **sales**] Return the total sales (price * move/qty) for each product. The output should have the UPC of a product and the total sales of that product for all stores and for all time.
- [Group by statement](https://www.w3schools.com/mysql/mysql_groupby.asp)

```
# code here

```


+----------------------------------------------------------------------------+
| **Well done!!!**                                                           |
| Now rename this file as `studentID.md` and submit on canvas.               |
| Enjoy the rest of your week and good luck on midterm!                      |
+----------------------------------------------------------------------------+
