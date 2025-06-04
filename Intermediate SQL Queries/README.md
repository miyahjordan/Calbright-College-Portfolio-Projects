<h1 align="center">Intermediate SQL Queries Project</h1>

<br><p align="center">A project focusing on writing and explaining SQL queries to ensure full comprehension and demonstrate skills. Made up of 5 tasks to complete and show proof of queries.</p>

<br><h2>🧭 Table of Contents</h2>
- <a href="https://github.com/miyahj/Calbright-College-Portfolio-Projects/edit/main/Intermediate%20SQL%20Queries/README.md#-task-1">Task 1</a>
- <a href="https://github.com/miyahj/Calbright-College-Portfolio-Projects/edit/main/Intermediate%20SQL%20Queries/README.md#-task-2">Task 2</a>
- <a href="https://github.com/miyahj/Calbright-College-Portfolio-Projects/edit/main/Intermediate%20SQL%20Queries/README.md#-task-3">Task 3</a>
- <a href="https://github.com/miyahj/Calbright-College-Portfolio-Projects/edit/main/Intermediate%20SQL%20Queries/README.md#-task-4">Task 4</a>
- <a href="https://github.com/miyahj/Calbright-College-Portfolio-Projects/edit/main/Intermediate%20SQL%20Queries/README.md#-task-5">Task 5</a>
- <a href="https://github.com/miyahj/Calbright-College-Portfolio-Projects/tree/main">back to main page</a>

<br><h2>✨ Task #1</h2>
Write a SQL query that retrieves a list of all people including their id number, first name, last name, age, and state code.

```sql
SELECT id_number, first_name, last_name, age, state_code
FROM people
```

<table>
  <tr>
    <th>id_number</th>
    <th>first_name</th>
    <th>last_name</th>
    <th>age</th>
    <th>state_code</th>
  </tr>
  <tr>
    <td>1</td>
    <td>Janice</td>
    <td>Howell</td>
    <td>44</td>
    <td>CA</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Wanda</td>
    <td>Alverez</td>
    <td>33</td>
    <td>CA</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Laura</td>
    <td>Olsen</td>
    <td>40</td>
    <td>CA</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Jack</td>
    <td>Garcia</td>
    <td>55</td>
    <td>NY</td>
  </tr>
  <tr>
    <td>5</td>
    <td>Ryan</td>
    <td>Rice</td>
    <td>57</td>
    <td>DE</td>
  </tr>
</table>

In this query, I picked the id number, first name, last name, age, and state code columns from the people table. As a result, the query returned a table with 1000 entries* with the columns selected. 
<br>*For the sake of this portfolio, I only copied the first five results. If necessary, will use this method display to show results throughout the document.

<br><h2>✨ Task #2</h2>
Write a SQL query that retrieves a list of all people including their id number, first name, last name, age, and state code who have a state code of CA. How many rows of data are in the result

```sql
SELECT id_number, first_name, last_name, age, state_code
FROM people
WHERE state_code = 'CA'
```

<table>
  <tr>
    <th>id_number</th>
    <th>first_name</th>
    <th>last_name</th>
    <th>age</th>
    <th>state_code</th>
  </tr>
  <tr>
    <td>1</td>
    <td>Janice</td>
    <td>Howell</td>
    <td>44</td>
    <td>CA</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Wanda</td>
    <td>Alverez</td>
    <td>33</td>
    <td>CA</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Laura</td>
    <td>Olsen</td>
    <td>40</td>
    <td>CA</td>
  </tr>
  <tr>
    <td>15</td>
    <td>Linda</td>
    <td>Mitchell</td>
    <td>47</td>
    <td>CA</td>
  </tr>
  <tr>
    <td>19</td>
    <td>Robin</td>
    <td>Hayes</td>
    <td>27</td>
    <td>CA</td>
  </tr>
</table>

This query produces a table with 127 rows filled with the first names, last names, ages, and id numbers of every person that lives in California.

<br><h2>✨ Task #3</h2>
Write a SQL query that finds the first name, last name, and age of the oldest person in the people table. Is it just one person, or are there actually multiple people who are the same age?

```sql
SELECT first_name, last_name, MAX(age) AS oldest_age
FROM people
```

<table>
  <tr>
    <th>first_name</th>
    <th>last_name</th>
    <th>oldest_age</th>
  </tr>
  <tr>
    <td>Paula</td>
    <td>Montgomery</td>
    <td>60</td>
  </tr>
</table>

This query utilizes the MAX function to find the largest number in the age column. I also renamed the MAX(age) column to oldest_age using AS to make the purpose of the column clear. It also produces a result that only shows the first and last name of the person/people. In this case, there is only one person in the people table who meets the criteria and is 60 years old, Paula Montgomery.

<br><h2>✨ Task #4</h2>
Write a SQL query that lists the city, state code, and state name for every record in the people table

```sql
SELECT DISTINCT p.city, s.state_name, p.state_code
FROM people p
LEFT JOIN states s
ON p,state_code = s.state_abbrev
ORDER BY s.state_name, p.city
```

<table>
  <tr>
    <th>city</th>
    <th>state_code</th>
    <th>state_name</th>
  </tr>
  <tr>
    <td>Brimingham</td>
    <td>Alabama</td>
    <td>AL</td>
  </tr>
  <tr>
    <td>Hunstvile</td>
    <td>Alabama</td>
    <td>AL</td>
  </tr>
  <tr>
    <td>Mobile</td>
    <td>Alabama</td>
    <td>AL</td>
  </tr>
  <tr>
    <td>Montgomery</td>
    <td>Alabama</td>
    <td>AL</td>
  </tr>
  <tr>
    <td>Tuscaloosa</td>
    <td>Alabama</td>
    <td>AL</td>
  </tr>
  <tr>
    <td>Anchorage</td>
    <td>Alaska</td>
    <td>AK</td>
  </tr>
  <tr>
    <td>Apache Junction</td>
    <td>Arizona</td>
    <td>AZ</td>
  </tr>
</table>

For this query, I selected the city and state code columns from the people table and the state name column from the states table. To initiate my join, I decided to use the people table for my FROM clause, then used a LEFT JOIN for the states table. To keep track of where the columns are from, I aliased the tables with p and s for people and states, respectively. I then joined the tables on the state code and state abbrev columns because the state code acts as a foreign key. From there I used the ORDER BY clause to order the table by state, then by city names. To avoid multiple instances of a city popping up, I added the DISTINCT function to my SELECT statement.


<br><h2>✨ Task #5</h2>
Write a SQL query that finds the average quiz points value for people from the City of Los Angeles.

```sql
SELECT city, AVG(quiz_points) AS average_quiz_points
FROM people
WHERE city = 'Los Angeles'
```

<table>
  <tr>
    <th>88.111</th>
    <th>Los Angeles</th>
  </tr>
  <tr>
    <th>average_quiz_points</th>
    <th>city</th>
  </tr>
</table>

To get this result, I selected the quiz points and city columns from the people table. Since we need to find the average, I used the AVG function on the quiz points column and renamed it to average quiz points for clarity. Then, I used the WHERE clause to narrow down our search to Los Angeles.
