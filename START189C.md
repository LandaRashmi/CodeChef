🚀 CodeChef Weekly Upload – Starters 189 Division 3  
🗓️ Date: 4 June 2025  
📁 Contest: Starters 189 Division 3  
🎯 Difficulty: Intermediate  
👨‍💻 Language: Python  

📈 Note:  
Solved 3 problems in this round — all required careful logic and efficient iteration. A solid performance!

---

🧩 **Problem 1: Distinct Two Subarray (DIS2SUB)**  
🔗 [Link to Problem](https://www.codechef.com/problems/DIS2SUB)  
🚩 Difficulty: Intermediate  

📝 **Problem Statement (Short Summary)**  
Given an array `a`, find the length of the **shortest subarray** that contains **exactly 2 distinct elements**.  
If no such subarray exists, return `-1`.

✅ **My Code**
```python
def f(a):
  n = len(a)
  m = float('inf')
  for i in range(n):
    d = {}
    for j in range(i, n):
      d[a[j]] = d.get(a[j], 0) + 1
      if len(d) > 2:
        break
      if len(d) == 2:
        m = min(m, j - i + 1)
  return m if m != float('inf') else -1

t = int(input())
for _ in range(t):
  n = int(input())
  a = list(map(int, input().split()))
  print(f(a))
```
💡 **Explanation**  

For every starting index, use a sliding window to find the shortest valid subarray

Stop when the window exceeds 2 distinct elements

Track the minimum length across all

🧠 Time Complexity: O(n²)  
📦 Space Complexity: O(n)

---


🧩 **Problem 2: Nutrition Cost (NUTRICOST)**  
🔗 [Link to Problem](https://www.codechef.com/problems/NUTRICOST)   
🚩 Difficulty: Intermediate   

📝 **Problem Statement (Short Summary)**   
You're given n food items, each with a category and cost.   
You can select at most one food from each category.   
For selecting i items, gain c × i energy but spend the sum of their costs.  
Maximize the net energy = c × i − cost sum.  

✅ **My Code**  
```python

t = int(input())
for _ in range(t):
  n, c = map(int, input().split())
  a = list(map(int, input().split()))
  b = list(map(int, input().split()))
  d = {}
  for i in range(n):
    if a[i] not in d or b[i] < d[a[i]]:
      d[a[i]] = b[i]
  v = sorted(d.values())
  s = 0
  m = 0
  for i in range(len(v)):
    s += v[i]
    m = max(m, c * (i + 1) - s)
  print(m)


```
💡 **Explanation**  

For each category, keep only the minimum cost

Sort the selected costs and evaluate net energy for top i foods

Return the maximum

🧠 Time Complexity: O(n log n)  
📦 Space Complexity: O(n)

---


🧩 **Problem 3: Create Binary String (CREATEBINSTR)**  
🔗 [Link to Problem](https://www.codechef.com/problems/CREATEBINSTR)      
🚩 Difficulty: Intermediate    

📝 **Problem Statement (Short Summary)**  
You need to construct a binary string of length n with 0s and 1s.  
For each 0, you get a points; for each 1, b points.  
Each (0,1) pair gives c points if c ≥ d, otherwise gives d.  
Maximize total score.  

✅ **My Code**  
```python

t = int(input())
for _ in range(t):
  n, a, b, c, d = map(int, input().split())
  m = 0
  for k in range(n + 1):
    z = k
    o = n - k
    s = z * a + o * b
    if c >= d:
      s += z * o * c
    else:
      s += z * o * d
    m = max(m, s)
  print(m)



```
💡 **Explanation**  

Try all combinations of 0s (z) and 1s (o = n - z)

Calculate score for each and keep the max

Consider both possibilities of pair bonus c vs d

🧠 Time Complexity: O(n)  
📦 Space Complexity: O(1)

---

