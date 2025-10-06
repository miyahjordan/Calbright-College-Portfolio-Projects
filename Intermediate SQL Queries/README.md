<h1 align='center'>Intermediate SQL Queries - Population Data</h1>

### Executive Summary:
Using MySQL, I pulled data from the database to answer 5 exploratory data analysis questions pertaining to the project:
    
1. Write a SQL query that retrieves a list of all people including their id number, first name, last name, age, and state code.
   - There are 1000 rows in the database
2. Write a SQL query that retrieves a list of all people including their id number, first name, last name, age, and state code who have a state code of CA. How many rows of data are in the result?
   - There are 127 rows of data for every resident that lives in California
3. Write a SQL query that finds the first name, last name, and age of the oldest person in the people table. Is it just one person, or are there actually multiple people who are the same age?
   - The oldest age in the database is 60 years old, and the oldest person is Paula Montgomery
4. Write a SQL query that lists the city, state code, and state name for every record in the people table.
5. Write a SQL query that finds the average quiz points value for people from the City of Los Angeles.
   - The average quiz point value from people living in Los Angeles is 88.111
  
After answering the questions, I documented my queries, the results, and an explanation of my findings:

### Business Problem:
Retreiving data from a database is essential to conudcting data analysis. Calbright college provided a dataset filled with fabricated population data across the United States so students can display their SQL skills. Five questions were assigned to conduct exploratory analysis on the dataset, how can we use SQL queries to answer them?

### Methodology:
Creating SQL queries that transforms and extracts data from the database.

### Skills:
SQL: Joins, Aggregate functions

### Results:
1. Write a SQL query that retrieves a list of all people including their id number, first name, last name, age, and state code.

  <table align='center'>
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
*For the sake of this portfolio, I only copied the first five results. If necessary, will use this method display to show results throughout the document.

2. Write a SQL query that retrieves a list of all people including their id number, first name, last name, age, and state code who have a state code of CA. How many rows of data are in the result

  <table align='center'>
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

3. Write a SQL query that finds the first name, last name, and age of the oldest person in the people table. Is it just one person, or are there actually multiple people who are the same age?

  <table align='center'>
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

4. Write a SQL query that lists the city, state code, and state name for every record in the people table.
  
  <table align='center'>
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

5. Write a SQL query that finds the average quiz points value for people from the City of Los Angeles.
  
  <table align='center'>
    <tr> 
      <th>city</th>
      <th>average_quiz_points</th>
      </tr>
    <tr>
      <th>Los Angeles</th>
      <th>88.111</th>
    </tr>
  </table>

To get this result, I selected the quiz points and city columns from the people table. Since we need to find the average, I used the AVG function on the quiz points column and renamed it to average quiz points for clarity. Then, I used the WHERE clause to narrow down our search to Los Angeles.
