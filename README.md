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
