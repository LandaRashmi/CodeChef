🚀 CodeChef Weekly Upload – Starters 190 Division 3  
🗓️ Date: 11 June 2025  
📁 Contest: Starters 190 Division 3  
🎯 Difficulty: Intermediate  
👨‍💻 Language: Python  

📉 Note:  
Faced challenges in this round — 2 wrong submissions on `RED23`, and couldn't solve `ORSUBSORT`. Still, learned better dynamic programming memoization and update optimization!  
The difficulty has increased noticabily in codechef..!

---

🧩 **Problem 1: Reduce to 2 or 3 (RED23)**  
🔗 [Link to Problem](https://www.codechef.com/problems/RED23)  
🚩 Difficulty: Intermediate  

📝 **Problem Statement (Short Summary)**  
Given an integer `x`, you can reduce it by:
- Subtracting 3 (if `x > 3`)
- Dividing by 2 (if `x % 2 == 0`)  
You want to reduce it to `1` or `3` using the **minimum number of operations**.  

✅ **My Code**
```python
from functools import lru_cache

@lru_cache(maxsize=None)
def f(x):
  if x <= 0:
    return float('inf')
  if x == 1 or x == 3:
    return x
  res = []
  if x > 3:
    res.append(f(x - 3))
  if x % 2 == 0:
    res.append(f(x // 2))
  return min(res)

t = int(input())
for _ in range(t):
  x = int(input())
  print(f(x))
```
💡 **Explanation**  

Use recursion with memoization (lru_cache)

Try both operations and take the min
⚠️ Note: The base cases return the value itself (1 or 3) instead of the step count, which caused wrong submissions. Should count steps instead.

🧠 Time Complexity: O(log x) with memoization  
📦 Space Complexity: O(x)

---


🧩 **Problem 2: Light Them All (LTALL)**  
🔗 [Link to Problem](https://www.codechef.com/problems/LTALL)    
🚩 Difficulty: Intermediate  

📝 **Problem Statement (Short Summary)**  
Given a string of bulbs ('0' for off, '1' for a switch), toggle bulbs in such a way that every bulb is on.  
A switch '1' can light its own, previous, or next position, in that priority order.

✅ **My Code**  
```python

t = int(input())
for _ in range(t):
  n = int(input())
  s = input().strip()
  lit = [False] * n

  for i in range(n):
    if s[i] == '1':
      if i > 0 and not lit[i - 1]:
        lit[i - 1] = True
        lit[i] = True
      elif i < n - 1 and not lit[i + 1]:
        lit[i] = True
        lit[i + 1] = True
      else:
        lit[i] = True

  print("Yes" if all(lit) else "No")



```
💡 **Explanation**  

Traverse and greedily light adjacent or own positions

Track which positions are lit

Final answer depends on whether all positions are lit

🧠 Time Complexity: O(n)  
📦 Space Complexity: O(n)

---



🧩 **Problem 3: Min Max Delete (MNMXDEL)**  
🔗 [Link to Problem](https://www.codechef.com/problems/MNMXDEL)    
🚩 Difficulty: Intermediate  

📝 **Problem Statement (Short Summary)**  
You’re given an array and must maintain the sum of min(a[i], a[i+1]) for all i in 0 to n-2 after multiple update queries.

✅ **My Code**  
```python

t = int(input())
for _ in range(t):
  n, q = map(int, input().split())
  a = list(map(int, input().split()))
  s = sum(min(a[i], a[i + 1]) for i in range(n - 1))
  for _ in range(q):
    i, x = map(int, input().split())
    i -= 1
    if i > 0:
      s -= min(a[i], a[i - 1])
    if i < n - 1:
      s -= min(a[i], a[i + 1])
    a[i] = x
    if i > 0:
      s += min(a[i], a[i - 1])
    if i < n - 1:
      s += min(a[i], a[i + 1])
    print(s)



```
💡 **Explanation**  

Precompute the total sum

For each update, remove contributions of a[i] from its neighbors

Then add new contributions after update

🧠 Time Complexity: O(1) per query  
📦 Space Complexity: O(1)

---


🧩 **Problem 4: OR Subsort (ORSUBSORT)**  
🔗 [Link to Problem](https://www.codechef.com/problems/ORSUBSORT)    
🚩 Difficulty: Hard (Unsolved)  

📝 **Problem Statement (Short Summary)**  
Given a range [l, r], find an integer x such that l <= x <= r and x | y == x for all y in [l, r].  
In other words, find the minimum x in that range such that OR with any number doesn't change x.

**⚠️ Attempted but got wrong submission.**

**💡 Concept Insight (Post-Analysis)**

Such an x must have 1s in all the positions where any number in range [l, r] has 1

So, compute OR of all values from l to r

But range is large → use bit position trick or bounds observation
(Not implemented in contest)

🧠 Expected Time Complexity: O(1) using bit math  
📦 Space Complexity: O(1)

---



