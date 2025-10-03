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
6. a
7. a
8. a
9. a
10. a
11. a

12. a
13. a
14. a
15. a
16. a

17. a
18. a
19. a
20. a
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

50. a
