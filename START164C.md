🚀 CodeChef Weekly Upload – Starters 164 Division 3  
🗓️ Date: 11 December 2024  
📁 Contest: Starters 164 Division 3  
🎯 Difficulty: Beginner  
👨‍💻 Language: Python  

---

🧩 **Problem 1: SPC2025Q2**  
🔗 [Link to Problem](https://www.codechef.com/problems/SPC2025Q2)  
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
You are given an array `a` of `n` integers, and two integers `k` and `p`.  
- Ved gets `k + max(a)` points  
- Varun gets `k + p + sum(a) - max(a)` points  
Determine who has more points or if it's equal.

✅ **My Code**
```python
t = int(input())
for _ in range(t):
  n, k, p = map(int, input().split())
  a = list(map(int, input().split()))
  x = k + max(a)
  y = k + p + sum(a) - x
  if x == y:
    print("Equal")
  elif x > y:
    print("Ved")
  else:
    print("Varun")
```
💡 **Explanation**

x = Ved's score = k + max(a)

y = Varun's score = k + p + sum(a) - max(a)

Compare x and y to determine the result

🧠 Time Complexity: O(n) per test case
📦 Space Complexity: O(1)

---
🥲 Solved only one question and my rating went down to 1⭐
