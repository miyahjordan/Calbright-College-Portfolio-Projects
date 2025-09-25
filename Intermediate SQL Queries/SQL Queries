-- Write a SQL query that retrieves a list of all people including their id number, first name, last name, age, and state code.

SELECT id_number, first_name, last_name, age, state_code
FROM people

-- Write a SQL query that retrieves a list of all people including their id number, first name, last name, age, and state code who have a state code of CA. 
-- How many rows of data are in the result 

SELECT id_number, first_name, last_name, age, state_code
FROM people
WHERE state_code = 'CA'

-- Write a SQL query that finds the first name, last name, and age of the oldest person in the people table. 
-- Is it just one person, or are there actually multiple people who are the same age?

SELECT first_name, last_name, MAX(age) AS oldest_age
FROM people

-- Write a SQL query that lists the city, state code, and state name for every record in the people table

SELECT DISTINCT p.city, s.state_name, p.state_code
FROM people p
LEFT JOIN states s
ON p,state_code = s.state_abbrev
ORDER BY s.state_name, p.city

-- Write a SQL query that finds the average quiz points value for people from the City of Los Angeles.

SELECT city, AVG(quiz_points) AS average_quiz_points
FROM people
WHERE city = 'Los Angeles'
