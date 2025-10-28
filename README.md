# Leetcode-SQL-50
Solutions for [SQL 50](https://leetcode.com/studyplan/top-sql-50/) - LeetCode 

---
1. [1757 - Recyclable and Low Fat Products](https://leetcode.com/problems/recyclable-and-low-fat-products/)
```sql
SELECT product_id
FROM Products
WHERE low_fats = 'Y'
AND recyclable = 'Y'
```

2. [584 - Find Customer Referee](https://leetcode.com/problems/find-customer-referee)
```sql
SELECT name 
FROM Customer 
WHERE referee_id != 2 OR referee_id IS null
```

3. [595 - Big Countries](https://leetcode.com/problems/big-countries/)
```sql
SELECT name, population, area
FROM WORLD
WHERE area >= 3000000
OR population >= 25000000
```

4. [1148 - Article Views I](https://leetcode.com/problems/article-views-i)
```sql
SELECT DISTINCT author_id as id
FROM Views
WHERE viewer_id >= 1
AND author_id = viewer_id
ORDER BY author_id
```
5. [1683 - Invalid Tweets](https://leetcode.com/problems/invalid-tweets/)
```sql
SELECT tweet_id
FROM Tweets
WHERE length(content) > 15
```
6. [1378 - Replace Employee ID With The Unique Identifier](https://leetcode.com/problems/replace-employee-id-with-the-unique-identifier)
```sql
SELECT unique_id, name
FROM Employees
LEFT JOIN EmployeeUNI 
ON Employees.id = EmployeeUNI.id
```
7. [1068 - Product Sales Analysis I](https://leetcode.com/problems/product-sales-analysis-i/)
```sql
SELECT product_name, year, price
FROM Product
INNER JOIN Sales ON Product.product_id = Sales.product_id
```
8. [1581 - Customer Who Visited but Did Not Make Any Transactions](https://leetcode.com/problems/customer-who-visited-but-did-not-make-any-transactions/)
```sql
SELECT customer_id, COUNT(*) as count_no_trans
FROM Visits 
WHERE visit_id NOT IN (SELECT DISTINCT visit_id FROM Transactions)
GROUP BY customer_id
```
9. [197 - Rising Temperature](https://leetcode.com/problems/rising-temperature/) 
```sql
SELECT table1.id
FROM Weather table1, Weather table2
WHERE DATEDIFF(table1.recordDate, table2.recordDate) = 1
AND table1.temperature > table2.temperature
```
10. 
[1661 - Average Time of Process per Machine](https://leetcode.com/problems/average-time-of-process-per-machine/)
```sql
SELECT machine_id, ROUND(AVG(end_t - start_t),3) AS processing_time
FROM
(SELECT machine_id, process_id, 
    MAX(CASE WHEN activity_type = 'start' THEN timestamp END) AS start_t,
    MAX(CASE WHEN activity_type = 'end' THEN timestamp END) AS end_t
 FROM Activity 
  GROUP BY machine_id, process_id) AS sorting
GROUP BY machine_id
```
11. [577 - Employee Bonus](https://leetcode.com/problems/employee-bonus/solutions/)
```sql
SELECT name, bonus
FROM Employee
LEFT JOIN Bonus ON Employee.empId = Bonus.empId
WHERE bonus < 1000 OR bonus IS NULL
```
12. [1280 - Students and Examinations](https://leetcode.com/problems/students-and-examinations/)
```sql
SELECT stu.student_id, stu.student_name, sub.subject_name, COUNT(exa.subject_name) AS attended_exams
FROM Students stu
JOIN Subjects sub
LEFT JOIN Examinations exa
ON stu.student_id = exa.student_id
AND sub.subject_name = exa.subject_name
GROUP BY stu.student_id, sub.subject_name
ORDER BY stu.student_id, sub.subject_name
```
13. [570. Managers with at Least 5 Direct Reports](https://leetcode.com/problems/managers-with-at-least-5-direct-reports)
```sql
SELECT e1.name
FROM Employee e1
JOIN Employee e2
ON e1.id = e2.managerId
GROUP BY e1.id
HAVING COUNT(e2.id) >= 5;
```
14. [1934. Confirmation Rate](https://leetcode.com/problems/confirmation-rate/)
```sql
SELECT sig.user_id, ROUND(AVG(IF(conf.action = 'confirmed',1,0)),2) AS confirmation_rate
FROM Signups as sig
LEFT JOIN Confirmations AS conf ON sig.user_id = conf.user_id
GROUP BY sig.user_id;
```
15. [620. Not Boring Movies](https://leetcode.com/problems/not-boring-movies)
```sql
SELECT *
FROM Cinema
WHERE id % 2 <> 0 
AND description <> "boring"
ORDER BY rating DESC
```
16. [1251. Average Selling Price](https://leetcode.com/problems/average-selling-price/)
```sql
SELECT p.product_id, COALESCE(ROUND(SUM(price * units) / SUM(units), 2),0) AS average_price
FROM Prices p
LEFT JOIN UnitsSold s
ON p.product_id = s.product_id 
AND purchase_date BETWEEN start_date AND end_date
GROUP BY p.product_id
```
17. 
[1075. Project Employees I](https://leetcode.com/problems/project-employees-i)
```sql
SELECT project_id, ROUND(AVG(experience_years), 2) average_years
FROM Project p 
LEFT JOIN Employee e
ON p.employee_id = e.employee_id
GROUP BY project_id
```
18. [1633. Percentage of Users Attended a Contest](https://leetcode.com/problems/percentage-of-users-attended-a-contest)
```sql
SELECT r.contest_id, ROUND(COUNT(DISTINCT r.user_id) * 100 / (SELECT COUNT(DISTINCT user_id) FROM Users), 2) AS percentage
FROM Register r
GROUP BY r.contest_id
ORDER BY percentage DESC, r.contest_id ASC;
```
19. [1211 Queries Quality and Percentage](https://leetcode.com/problems/queries-quality-and-percentage)
```sql
SELECT query_name, ROUND(AVG(rating/position), 2) AS quality,
ROUND(SUM(CASE WHEN rating < 3 THEN 1 ELSE 0 END) / COUNT(rating) * 100, 2) AS poor_query_percentage
FROM Queries
GROUP BY query_name
```
20. [1193. Monthly Transactions I](https://leetcode.com/problems/monthly-transactions-i/)
```sql
SELECT DATE_FORMAT(trans_date, '%Y-%m') month, country, COUNT(state) trans_count, 
        SUM(IF(state = 'approved', 1, 0)) approved_count, 
        SUM(amount) trans_total_amount,
        SUM(IF(state = 'approved', amount, 0)) approved_total_amount
FROM Transactions
GROUP BY 1, 2
```
21. a
22. a
23. a
24. a
25. a

26. a
27. a
28. a
29. a

30. a
31. a
32. a
33. a

34. a
35. a
36. a
37. a
38. a

39. a
40. a
41. a
42. a

43. a
44. a
45. a
46. a
47. a

48. a

49. a
