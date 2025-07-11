🚀 CodeChef Weekly Upload – Starters 186 Division 3  
🗓️ Date: 14 May 2025  
📁 Contest: Starters 186 Division 3  
🎯 Difficulty: Beginner to Intermediate  
👨‍💻 Language: Python  

📈 Note:  
I solved 4 problems in this contest, my rating has increased as well — strong comeback and consistent performance!  

---

🧩 **Problem 1: Best Movie (BESTMOVIE)**  
🔗 [Link to Problem](https://www.codechef.com/problems/BESTMOVIE)  
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
Given `n` movies, each having a rating `a` (out of 10) and ticket price `b`, find the **minimum ticket price** among movies with rating at least 7.  
If no such movie exists, print `-1`.

✅ **My Code**
```python
t = int(input())
for _ in range(t):
  n = int(input())
  x = float('inf')
  for _ in range(n):
    a, b = map(int, input().split())
    if a >= 7:
      x = min(x, b)
  if x == float('inf'):
    print(-1)
  else:
    print(x)
```
**💡 Explanation**

Track the minimum price for movies with rating ≥ 7

If none meet the condition, return -1

🧠 Time Complexity: O(n)  
📦 Space Complexity: O(1)

---


🧩 **Problem 2: Approval Rating (APPROVAL)**  
🔗 [Link to Problem  ](https://www.codechef.com/problems/APPROVAL)  
🚩 Difficulty: Intermediate  

📝 **Problem Statement (Short Summary)**  
Given a list of 5 marks (each ≤ 10), find how many 100-rupee bribes (max 5) you must give to convert them to full marks (10), so that the average is at least 7.

✅ **My Code**
```python

t = int(input())
for _ in range(t):
  a = list(map(int, input().split()))
  s = sum(a)
  c = 0
  a.sort()
  i = 0
  while s / 5 < 7 and i < 5:
    s += 10 - a[i]
    c += 100
    i += 1
  print(c)



```
💡 **Explanation**

Sort to bribe the lowest scores first

Greedily bump scores to 10 until average ≥ 7

🧠 Time Complexity: O(1)  
📦 Space Complexity: O(1)

---


🧩 **Problem 3: Jumping the Array (JUMPAB)**  
🔗 [Link to Problem](https://www.codechef.com/problems/JUMPAB)  
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
You make n jumps.
Each jump is either of size a (forward) or b (backward).
Check whether it’s possible to reach total distance m in exactly n jumps.

✅ **My Code**
```python

t = int(input())
for _ in range(t):
  n, m, a, b = map(int, input().split())
  d = a - b
  num = m - n * b
  if d == 0:
    print("Yes" if m == n * a else "No")
  elif num % d == 0 and 0 <= num // d <= n:
    print("Yes")
  else:
    print("No")


```
💡 **Explanation**

Reformulate using number of forward and backward jumps

Reduce to a linear equation and check if a valid count of forward jumps exists

🧠 Time Complexity: O(1)  
📦 Space Complexity: O(1)

---


🧩 **Problem 4: Distinct Arrangement (DISTARR)**  
🔗 [Link to Problem](https://www.codechef.com/problems/DISTARR)      
🚩 Difficulty: Intermediate  

📝 **Problem Statement (Short Summary)**  
Given an array of n integers, count the number of ways to rearrange them such that after sorting, each a[i] > i.
Print the result modulo 998244353.

✅ **My Code**  
```python

m = 998244353
t = int(input())
for _ in range(t):
  n = int(input())
  a = list(map(int, input().split()))
  a.sort()
  r = 1
  for i in range(n):
    x = a[i] - i
    if x <= 0:
      r = 0
      break
    r = r * x % m
  print(r)


```
💡 **Explanation**  

After sorting, for every index i, ensure a[i] > i

Multiply all valid (a[i] - i) choices

If any are invalid (≤ 0), answer is 0

🧠 Time Complexity: O(n log n)  
📦 Space Complexity: O(1)

---

