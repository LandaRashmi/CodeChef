🚀 CodeChef Weekly Upload – Starters 188 Division 3  
🗓️ Date: 31 July 2025  
📁 Contest: Starters 188 Division 3  
🎯 Difficulty: Beginner to Intermediate  
👨‍💻 Language: Python  

📈 Note:  
Successfully solved 4 problems — efficient implementation and TLE fix helped strengthen my problem-solving confidence!

---

🧩 **Problem 1: Train Even-Odd (TRAINEVOD)**  
🔗 [Link to Problem](https://www.codechef.com/problems/TRAINEVOD)  
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
Given a list of `n` coaches, each with a value.  
Odd and even indexed coaches are assigned to different teams.  
Find which team has a higher total sum of values and print the maximum.

✅ **My Code**
```python
t = int(input())
for _ in range(t):
  n = int(input())
  a = list(map(int, input().split()))
  x = sum(a[i] for i in range(0, n, 2))
  y = sum(a[i] for i in range(1, n, 2))
  print(max(x, y))
```
💡 **Explanation**  

Compute the sum at even indices and odd indices

Return the larger of the two

🧠 Time Complexity: O(n)  
📦 Space Complexity: O(1)

---


🧩 **Problem 2: Subset Sum Modulo 3 (SUBSUM3)**  
🔗 [Link to Problem](https://www.codechef.com/problems/SUBSUM3)      
🚩 Difficulty: Intermediate    

📝 **Problem Statement (Short Summary)**  
Given an array a, determine if any non-empty subset has a sum divisible by 3.

✅ **My Code**  
```python

def solution(a):
  s = set()
  for x in a:
    t = set()
    t.add(x % 3)
    for y in s:
      t.add((y + x) % 3)
    s.update(t)
  return 0 in s

t = int(input())
for _ in range(t):
  n = int(input())
  a = list(map(int, input().split()))
  print("Yes" if solution(a) else "No")



```
💡 **Explanation**  

Use a set to track all modulo 3 sums from subsets

For each element, update possible sums

If 0 appears → found a valid subset

🧠 Time Complexity: O(n)  
📦 Space Complexity: O(1)

---


🧩 **Problem 3: Yet Another Monster (YETMON)**  
🔗 [Link to Problem](https://www.codechef.com/problems/YETMON)      
🚩 Difficulty: Intermediate  

📝 **Problem Statement (Short Summary)**  
Each monster i has strength a[i].
You can reduce any monster’s strength to any value below or equal to a[i].
Find the minimum possible maximum value after redistributing to all monsters.

✅ **My Code**  
```python

t = int(input())
for _ in range(t):
  n = int(input())
  a = list(map(int, input().split()))
  a.sort()
  r = n
  for i in range(n):
    r = min(r, a[i] + n - i - 1)
  print(r)



```
💡 **Explanation**  

Sort the array

For each index, consider a[i] + (n - i - 1)

Track the minimum over all such values

🧠 Time Complexity: O(n log n)    
📦 Space Complexity: O(1)

---



🧩 **Problem 4: K Boxes (KBOXES)**  
🔗 [Link to Problem](https://www.codechef.com/problems/KBOXES)      
🚩 Difficulty: Intermediate   

📝 **Problem Statement (Short Summary)**  
Given arrays a and b, for each element i, calculate the minimum sum of at most k elements from b values, where selection is done based on the sorted order of a.
Output the sum just before inserting the i-th element.

✅ **My Code**  
```python

import heapq
t = int(input())
for _ in range(t):
  n, k = map(int, input().split())
  a = list(map(int, input().split()))
  b = list(map(int, input().split()))
  z = sorted([(a[i], i, b[i]) for i in range(n)])
  h = []
  res = [0] * n
  s = 0
  for _, i, c in z:
    res[i] = s
    heapq.heappush(h, c)
    s += c
    if len(h) > k:
      s -= heapq.heappop(h)
  print(*res)



```
💡 **Explanation**  

Sort by a[i]

Maintain a min-heap of size at most k

Before inserting, store current heap sum for that index

🧠 Time Complexity: O(n log n)  
📦 Space Complexity: O(k)

---


