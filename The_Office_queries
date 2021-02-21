--Find all employees ordered by sex then by name
SELECT *
FROM employee
ORDER BY sex, first_name;

--Find the first 5 employees in the table
SELECT *
FROM employee
LIMIT 5;

--Find the first and the last names of all employees
SELECT first_name,last_name
FROM employee;

--Find the forename and surname of all employees
SELECT first_name AS forename, last_name AS surname
FROM employee;

--Find out all the different genders
SELECT DISTINCT sex
FROM employee;

--Find the number of employees
SELECT COUNT(emp_id)
FROM employee;

--Find the number of females employee born after 1970
SELECT COUNT(emp_id)
FROM employee
WHERE sex='F' AND birth_day > '1970-01-01';

--Find the average of all employee's salaries
SELECT AVG(salary)
FROM employee;

--Find the average of all male employee's salaries
SELECT AVG(salary)
FROM employee
WHERE sex='M';

--Find the sum of all employee's salaries
SELECT SUM(salary)
FROM employee;

--Find out how many males and females there are
SELECT COUNT(sex), sex
FROM employee
GROUP BY sex;

--WILDCARDS
-- % = any # characters, _ = one character
--Find any client's who are an LLC
SELECT *
FROM client
WHERE client_name LIKE '%LLC';

--Find any branch suppliers who are in the label business
SELECT *
FROM branch_supplier
WHERE supplier_name LIKE '%Label%';

--Find any employee born in October
SELECT *
FROM employee
WHERE birth_day LIKE '____-10%';

--Find any clients who are schools
SELECT *
FROM client
WHERE client_name LIKE '%school%';

--UNION
--Find a list of employee and branch names
SELECT first_name
FROM employee
UNION
SELECT branch_name
FROM branch;

--JOINS
INSERT INTO branch VALUES(4, 'Buffalo', NULL, NULL);
--Find all branches and the names of their managers
SELECT employee.emp_id, employee.first_name, branch.branch_name
FROM employee
JOIN branch
ON employee.emp_id = branch.mgr_id;

--NESTED QUERIES
--Find names of all employees who have sold over 30,000 to a single client
SELECT employee.first_name, employee.last_name
FROM employee
WHERE employee.emp_id IN(
    SELECT works_with.emp_id
    FROM works_with
    WHERE works_with.total_sales > 30000
);

--Find all client who are handled by the branch that Michael Scott manages
--Assume you know Michael's ID
SELECT client.client_name
FROM client
WHERE client.branch_id = (
    SELECT branch.branch_id
    FROM branch
    WHERE branch.mgr_id = 102
    LIMIT 1
);

