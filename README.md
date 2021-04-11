# Pewlett-Hackard-Analysis

## Overview
In order to prepare for the possible mass retirement exodus that could be upon the business, analysis was done to collect the athe titles for all employees currently eligible for retirement as well as the amount of current retirement eligible employees that would qualify for the mentorhsip program.    

## Results
-- Gathering the data for analysis found that there are  a large number of eligible employees that are within retirement age, born between 1952 and 1955.
-- Analysis conducted based on current title of retirement eligible employees again reduced the previous count as now only the most current title was considered in the collection.  Still excessively large at a bit above 90K eligible employees.
-- The analysis warns that for both the Senior Engineer and Senior Staff levels, there are between 28k - 29K retirement eligible employees.
-- There are 1549 employees eligible for the mentorship program most within the Senior Staff and Engineer levels.
**insert image of mentorship eligible EEs and Retiring titles

## Summary
-- Based on the current data, there will be a littl over 90,000 roles that will need to be filled should the full "silver tsunami" take place.
-- Based solely on the data provided for those current employees eligible for the mentorship program born in 1965, there are only 1549.   On this data, there is not enough that would meet the requirement to fill the "silver tsumanI" replacements.
-- Open the range of employees eligible for the mentorship program to include birth year of 1964 and 1963.

SELECT DISTINCT ON (e.emp_no) e.emp_no, e.first_name, e.last_name, e.birth_date, de.from_date, de.to_date, t.title
-- INTO mentorship_eligibility_1964to1965
FROM employees as e
LEFT JOIN dept_emp as de
ON e.emp_no = de.emp_no
INNER JOIN titles as t
ON e.emp_no = t.emp_no
WHERE (e.birth_date BETWEEN '1964-01-01' AND '1965-12-31') AND (de.to_date = '9999-01-01')
ORDER BY e.emp_no;

SELECT DISTINCT ON (e.emp_no) e.emp_no, e.first_name, e.last_name, e.birth_date, de.from_date, de.to_date, t.title
-- INTO mentorship_eligibility_1963to1965
FROM employees as e
LEFT JOIN dept_emp as de
ON e.emp_no = de.emp_no
INNER JOIN titles as t
ON e.emp_no = t.emp_no
WHERE (e.birth_date BETWEEN '1963-01-01' AND '1965-12-31') AND (de.to_date = '9999-01-01')
ORDER BY e.emp_no;