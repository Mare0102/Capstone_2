# Capstone_2

The Sakila Database holds information about a company that rents movie DVDs. For this project, we will explore the database to gain more insight focusing on **Film**. This project will focused on 2 tables, that we will query through SQL.

1. Film focused table
2. Rental duration, Sales and Country

![sakila](https://www.jooq.org/img/sakila.png)

| No. | Table | Description
| :-- | -- | -- |
| 1 | actor | lists information for all actors |
| 2 | address | contains address information for customers, staff, and stores |
| 3 | category | lists the categories that can be assigned to a film |
| 4 | city | contains a list of cities |
| 5 | country | contains a list of countries |
| 6 | customer | contains a list of all customers |
| 7 | film | list of all films potentially in stock in the stores |
| 8 | film_actor | for each actor in a given film, there will be one row in the film_actor table listing the actor and film |
| 9 | film_category | for each category applied to a film, there will be one row in the film_category table listing the category and film |
| 10 | film_text | contains the film_id, title and description columns of the film table |
| 11 | inventory | contains one row for each copy of a given film in a given store |
| 12 | language | listing the possible languages that films can have for their language and original language values |
| 13 | payment | records each payment made by a customer, with information such as the amount and the rental being paid for |
| 14 | rental | contains one row for each rental of each inventory item with information about who rented what item, when it was rented, and when it was returned |
| 15 | staff | lists all staff members, including information for email address, login information, and picture |
| 16 | store | lists all stores in the system |

# Tables
From the database we will make 2 tables that can be used on our analysis.

## 1. **All About Film** (df_film)

In this table we will see a combination from 4 tables (category, film, language, inventory). This table will describe the Film's details, such as the inventory_id, category, title, release year, language, film length, rating, rental duration, and rental rate.

| Column | Table Origin | Description |
| :-- | :-- | :-- | 
| inventory_id | inventory | Number of inventory |
| category | category | Film category |
| title | film | Film title |
| release_year | film | Film release year |
| language | language | Film language |
| length | film | Film duration (in minutes) |
| rating | film | Film rating (G, PG, PG-13, etc) |
| rental_duration | film | Length of rental period in days | 
| rental_rate | film | Cost to rent the film for the period specified in the rental_duration |



## 2. **Rental Duration and Geography** (df_durcon)

In this table we will see a combination from 6 tables (rental, category, film, payment, country, city). This table will show the actual rental duration and actual income per category. We will also look if there are any geographical relation with the category.

| Column | Table Origin | Description |
| :-- | :-- | :-- |
| rental_id | rental | Unique key that identifies the rental |
| category | category | Film category |
| rating | film | Film rating (G, PG, PG-13, etc) |
| rental_rate | film | Cost to rent the film for the period specified in the rental_duration column |
| rental_duration | film | Length of the rental period in days |
| rental_length_day | film | Actual rental days (return_date - rental_date) |
| rental_date | rental | Actual rental day |
| payment | payment | The amount of payment (sum(amount)) |
| country | country | Where the rental takes place (country) |
| city | city | Where the rental takes place (city) |


# Data Manipulation
After we constructing the tables, we have to treat the missing values, change data type, and make new feature.

**df_film**
While there are no missing values on all the columns, we have wrong data type assigned to the rental_rate column. The rental_rate column is the rate of borrowing film in dollar. The data type should be float not object.

**df_durcon**
We have missing values on the rental_length_day and the wrong data type also assigned to the rental_rate and payment column. 

# Data Visualization & Statistics
In this section we will try to answer these questions:
1.	Where is our current inventory position?
2.	Total sales contribution according to category
3.	Can current inventory fulfil the customer’s need?
4.	Are there any difference on the average of the payment by category?
5.	What is the proportion of the payment that are overdue?
6.	Payment trend?
7.	Rental location increasing/decreasing?


P.S:
For some reason the output of ipynb file can't be loaded in this github. 
To view the output, please download and open the file on your preferred platform.
(change the MySQL user and password)


