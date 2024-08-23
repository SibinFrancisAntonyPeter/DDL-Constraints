# DDL-Constraints
create database Sales;
use Sales;
create table Orders(
Order_Id int primary key, 
Customer_name varchar(30), 
Product_Category varchar(30) not null, 
Ordered_item varchar(50) unique not null, 
Contact_No character(10)
);

desc Orders;

# 1) Add a new column named “order_quantity” to the orders table.
Alter table Orders
add column order_quantity int not null;

# 2) Rename the orders table to the sales_orders table.
Alter table Orders
rename to sales_orders;

desc sales_orders;

# 3 Insert 10 rows into the sales_orders table. 
insert into sales_orders values
(111, 'Abhijith', 'Electronics', 'Laptop', '9142315895', 1),
(222, 'Deepu', 'Home Appliances', 'Microwave', '9567724688', 2),
(333, 'Gokul', 'Electronics', 'Smartphone', '8606495819', 1),
(444, 'Hari', 'Beauty', 'Perfume', '8901234567', 1),
(555, 'Ivan', 'Sports', 'Basketball', '9012345678', 2),
(666, 'Jibin', 'Furniture', 'Sofaset', '9562113963', 2),
(777, 'Manu', 'Clothing', 'Jeans', '9074464862', 3),
(888, 'Pran', 'Personal Care', 'Hair Serum', '8891972903', 5),
(999, 'Salman', 'Books', 'Novel', '7736262928', 4),
(1010, 'Sante', 'Electronics', 'Tablet', '8075508257', 1);

select * from sales_orders;

# 4)Retrieve customer_name and Ordered_Item from the sales_orders table.
Select Customer_name, Ordered_item from sales_orders;

# 5) Use the update command to change the name of the product for any row. 
update sales_orders
SET Ordered_item = 'Smart TV' where Order_Id = 1010 ;

# 6) Delete the sales_orders table from the database.
drop table sales_orders;

