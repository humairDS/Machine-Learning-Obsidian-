## Practice Qs 1

Qs Create a database for your company names Xyz

==Step 1==:create a table inside this DB to store the employee info(id,name and salary).

==Step 2==: Add following information in the DB:
```INFO
1, "Adam",25000
2,"Bob",30000
3,"Casey",40000
```

==Step3==: Select & view all your table data


## Practice Qs 2

1. Write the Query to find avg marks in each city in ascending order.
2. For the given table , find the total payment according to each payment method.
```SQL 
CREATE TABLE info(
	customer_id INT PRIMARY KEY,
	customer VARCHAR(50), 
	mode VARCHAR(20),
	city VARCHAR(20)
);

INSERT INTO info
(customer_id,customer,mode,city)
VALUES
(101,"Umair","Netbanking","Karachi"),
(102,"Hamiz","Credit","Karachi"),
(103,"Ali","Debit","Turbat"),
(104,"Mairaj","Netbanking","Peshawar"),
(105,"Husban","Credit","Multan"),
(106,"Sameer","Credit","Lahore"),
(107,"Sundus","Credit","Karachi"),
(108,"Shaheer","Debit","Karachi"),
(109,"Warisha","Netbanking","Islamabad"),
(110,"Sumbul","Credit","Lahore");
```

```SQL 
SELECT mode, count(mode)
FROM info
GROUP BY mode;
```
