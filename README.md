# leetcode-sql
Practicing SQL through LeetCode problems, with clean queries and concise explanations.

# 1633. Percentage of Users Attended a Contest
**Platform:** LeetCode  
**Difficulty:** Easy  
**Link:** https://leetcode.com/problems/percentage-of-users-attended-a-contest/

## Approach
- Count distinct users per contest from the Register table
- Divide by total number of users
- Multiply by 100 and round to two decimals
- Sort by percentage (DESC) and contest_id (ASC)

## Complexity
- Time: O(R + U)
- Space: O(1)

## LeetCode Submission
Please check [My submitted solution](https://leetcode.com/problems/percentage-of-users-attended-a-contest/solutions/7443474/1633-percentage-of-users-attended-a-cont-87k0)

# Code
```postgresql []
SELECT
    contest_id,
    ROUND(COUNT(DISTINCT user_id) * 100.0 / (SELECT COUNT(*) FROM Users), 2) AS percentage
FROM Register
GROUP BY contest_id
ORDER BY percentage DESC, contest_id ASC;
```
