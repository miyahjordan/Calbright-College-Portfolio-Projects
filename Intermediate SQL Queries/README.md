<h1 align="center">Intermediate SQL Queries Project</h1>

<br><p align="center">A project focusing on writing and explainig SQL queries to ensure full comprehension and demonstrate skills. Made up of 5 tasks to complete and show proof of queries.</p>

<br><h2>🧭 Table of Contents</h2>
- <a href="https://github.com/miyahj/Calbright-College-Portfolio-Projects/edit/main/Intermediate%20SQL%20Queries/README.md#-task-1">Task 1</a>
- <a href="https://github.com/miyahj/Calbright-College-Portfolio-Projects/edit/main/Intermediate%20SQL%20Queries/README.md#-task-2">Task 2</a>
- <a href="https://github.com/miyahj/Calbright-College-Portfolio-Projects/edit/main/Intermediate%20SQL%20Queries/README.md#-task-3">Task 3</a>
- <a href="https://github.com/miyahj/Calbright-College-Portfolio-Projects/edit/main/Intermediate%20SQL%20Queries/README.md#-task-4">Task 4</a>
- <a href="https://github.com/miyahj/Calbright-College-Portfolio-Projects/edit/main/Intermediate%20SQL%20Queries/README.md#-task-5">Task 5</a>
- <a href="">back to main page</a>

<br><h2>✨ Task #1</h2>
Write a SQL query that retrieves a list of all people including their id number, first name, last name, age, and state code.

```
SELECT id_number, first_name, last_name, age, state_code
FROM people
```

In this query, I picked the id number, first name, last name, age, and state code columns from the people table. As a result, the query returned a table with all the columns selected and the data inside of them. The id number column produces integers from 1 to 1000, the first name column displays the first names of everyone in the table, the last name column displays the last names of everyone in the table, the age column shows the ages of everyone in the table and the state code shows the state where everyone in the table lives.



<br><h2>✨ Task #2</h2>
Write a SQL query that retrieves a list of all people including their id number, first name, last name, age, and state code who have a state code of CA. How many rows of data are in the result

```
```

This query produces a table with 127 rows filled with the first names, last names, ages, and id numbers of every person that lives in California.

<br><h2>✨ Task #3</h2>
Write a SQL query that finds the first name, last name, and age of the oldest person in the people table. Is it just one person, or are there actually multiple people who are the same age?

```
```

This query utilizes the MAX function to find the largest number in the age column. I also renamed the MAX(age) column to oldest_person using AS to make the purpose of the column clear. It also produces a result that only shows the first and last name of the person/people. In this case, there is only one person in the people table who meets the criteria and is 60 years old, Paula Montgomery.

<br><h2>✨ Task #4</h2>
Write a SQL query that lists the city, state code, and state name for every record in the people table

```
```

For this query, I selected the city and state code columns from the people table and the state name column from the states table. To initiate my join, I decided to use the people table for my FROM clause, then used a LEFT JOIN for the states table. To keep track of where the columns are from, I aliased the tables with p and s for people and states, respectively. I then joined the tables on the state code and state abbrev columns because the state code acts as a foreign key. From there I used the ORDER BY clause to order the table by state, then by city names. To avoid multiple instances of a city popping up, I added the DISTINCT function to my SELECT statement.


<br><h2>✨ Task #5</h2>
Write a SQL query that finds the average quiz points value for people from the City of Los Angeles.

```
```

To get this result, I selected the quiz points and city columns from the people table. Since we need to find the average, I used the AVG function on the quiz points column and renamed it to average quiz points for clarity. Then, I used the WHERE clause to narrow down our search to Los Angeles.
