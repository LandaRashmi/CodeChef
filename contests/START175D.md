🚀 CodeChef Weekly Upload – Starters 175 Division 4  
🗓️ Date: 26 February 2025  
📁 Contest: Starters 175 Division 4  
🎯 Difficulty: Beginner  
👨‍💻 Language: Python  

📈 **Note:**  
I was able to solve **two problems** in this contest — a good improvement from previous weeks. Small steps back toward climbing the ladder from **1★ upward**!

---

🧩 **Problem 1: Minimum Number of Pages (P1_175)**  
🔗 [Link to Problem](https://www.codechef.com/problems/P1_175)  
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
Chef has to read `x` pages and has `y` days left.  
Determine if he can finish reading all the pages — i.e., `x <= y`.

✅ **My Code**
```python
x, y = map(int, input().split())
if x <= y:
  print("YES")
else:
  print("NO")
```
💡 **Explanation**

Straightforward comparison between pages and days

If x <= y, output "YES", else "NO"

🧠 Time Complexity: O(1)

📦 Space Complexity: O(1)

---


🧩 **Problem 2: Chef and Triangle (P2_175)**  
🔗 [Link to Problem](https://www.codechef.com/problems/P2_175)
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  

Given a value n, determine the number of tiles needed to form a triangle of n height according to a pattern:

For n=1 or n=3, output 1

For n=2, output 2

Otherwise, calculate based on even/odd properties

✅ **My Code**
```python

def res(n):
  if n == 1 or n == 3:
    return 1
  elif n == 2:
    return 2
  else:
    if n % 2 == 0:
      return n // 2 + 1
    else:
      return n // 2

t = int(input())
for _ in range(t):
  n = int(input())
  print(res(n))


```
💡 **Explanation**

Special handling for n = 1, 2, 3

For n > 3, logic based on parity of n

If even: result is n // 2 + 1

If odd: result is n // 2

🧠 Time Complexity: O(1) per test case

📦 Space Complexity: O(1)

---

