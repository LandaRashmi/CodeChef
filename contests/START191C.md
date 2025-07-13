🚀 CodeChef Weekly Upload – Starters 191 Division 3  
🗓️ Date: 18 June 2025  
📁 Contest: Starters 191 Division 3  
🎯 Difficulty: Beginner to Advanced  
👨‍💻 Language: Python  

📈 Note:  
Solved 4 problems, with one wrong submission on `PERMGE2`. The last problem (`SUB12`) required a neat binary search approach — a great wrap-up to this round!

---

🧩 **Problem 1: Nearest Perfect Square (NEARSQ)**  
🔗 [Link to Problem](https://www.codechef.com/problems/NEARSQ)  
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
Given a number `n`, find the largest perfect square less than or equal to `n`.

✅ **My Code**
```python
t = int(input())
for _ in range(t):
  n = int(input())
  a = int(n ** 0.5)
  print(a * a)
```
💡 **Explanation**  

Compute integer square root of n, then square it

Result is the nearest perfect square ≤ n

🧠 Time Complexity: O(1)   
📦 Space Complexity: O(1)

---


🧩 **Problem 2: Add to Make GCD > 1 (ADDGCD)**  
🔗 [Link to Problem](https://www.codechef.com/problems/ADDGCD)   
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
Given integers x and y, return the minimum value to be added to either x or y to make gcd(x, y) > 1.

✅ **My Code**  
```python

import math
t = int(input())
for _ in range(t):
  x, y = map(int, input().split())
  if math.gcd(x, y) > 1:
    print(0)
  elif math.gcd(x + 1, y) > 1 or math.gcd(x, y + 1) > 1:
    print(1)
  else:
    print(2)


```
💡 **Explanation**  

Check original GCD

Then test incrementing x or y by 1

If not enough, print 2

🧠 Time Complexity: O(log(min(x, y)))  
📦 Space Complexity: O(1)

---


🧩 **Problem 3: Permutation Game 2 (PERMGE2)**  
🔗 [Link to Problem](https://www.codechef.com/problems/PERMGE2)    
🚩 Difficulty: Intermediate  

📝 **Problem Statement (Short Summary)**  
You’re given integers x, y, and z.  
Determine if it’s possible to construct a permutation under certain movement constraints using swaps of adjacent elements (problem logic abstracted).

✅ **My Code**  
```python

t = int(input())
for _ in range(t):
  x, y, z = map(int, input().split())
  if x == 0:
    print("Yes")
  elif y == 0:
    print("Yes" if x <= z + 1 else "No")
  else:
    print("Yes" if x <= z else "No")


```
💡 **Explanation**  

x = number of required swaps

y = fixed points

z = buffer for movement

If y = 0, we get 1 extra move

If x == 0, always valid

🧠 Time Complexity: O(1)  
📦 Space Complexity: O(1)



---


🧩 **Problem 4: Subtraction Game 12 (SUB12)**  
🔗 [Link to Problem ](https://www.codechef.com/problems/SUB12)   
🚩 Difficulty: Advanced  

📝 **Problem Statement (Short Summary)**  
Given two arrays a and b, and a rule that lets you subtract a[i] from a number m, and reduce by up to b[i] from m - a[i], find the minimum m such that total reduction is at least sum of b.

✅ **My Code**  
```python

t = int(input())
for _ in range(t):
  n = int(input())
  a = list(map(int, input().split()))
  b = list(map(int, input().split()))
  s = sum(b)
  def ok(m):
    f = 0
    for i in range(n):
      d = m - a[i]
      if d < 0: return 0
      u = min(b[i], d)
      m2 = d >> 1
      if d & 1:
        f += m2 + ((u + 1) >> 1)
      else:
        f += m2 + (u >> 1)
      if f >= s: return 1
    return f >= s
  l = max(a)
  r = l + 2 * s
  while l < r:
    m = (l + r) // 2
    if ok(m): r = m
    else: l = m + 1
  print(l)



```
💡 **Explanation**  

Binary search on value of m

For each guess, check if it satisfies the condition using a greedy simulator

Adjust range accordingly

🧠 Time Complexity: O(n log s)  
📦 Space Complexity: O(1)

---

