🚀 CodeChef Weekly Upload – Starters 177 Division 3  
🗓️ Date: 12 March 2025  
📁 Contest: Starters 177 Division 3  
🎯 Difficulty: Beginner to Intermediate  
👨‍💻 Language: Python  

📈 **Note:**  
In this contest, I solved **three problems**—a positive move towards regaining rating from **1★ to 2★** soon!

---

🧩 **Problem 1: Triangle Check (TRICHECK)**  
🔗 [Link to Problem](https://www.codechef.com/problems/TRICHECK)  
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
Check if three given lengths `a, b, c` can form a valid triangle.  
That requires:
- `a + b > c`
- `b + c > a`
- `a + c > b`

✅ **My Code**
```python
a, b, c = map(int, input().split())
if a + b > c and b + c > a and a + c > b:
  print("Yes")
else:
  print("No")
```
💡 **Explanation**

Straightforward application of the triangle inequality conditions to verify if a triangle is possible.

🧠 Time Complexity: O(1)

📦 Space Complexity: O(1)

---


🧩 **Problem 2: Box to Meet Target (BOX2)**  
🔗 [Link to Problem](https://www.codechef.com/problems/BOX2)

🚩 Difficulty: Intermediate


📝 **Problem Statement (Short Summary)**  
Given two boxes containing x and y items respectively, and a target number k,
find the minimum number of moves to reach exactly k difference by moving items between them.
Rules:

You can move one item at a time.

If exact match is already present (|x – y| = k), answer is 0.

If it's impossible to reach exactly k, print -1.

✅ **My Code**
```python

def minDiff(x, y, k):
  diff = abs(x - y)
  if diff == k:
    return 0
  if (k - diff) % 2 == 1 or k > x + y:
    return -1
  return abs(k - diff) // 2

t = int(input())
for _ in range(t):
  x, y, k = map(int, input().split())
  print(minDiff(x, y, k))



```
💡 **Explanation**

Calculate current difference diff = |x - y|

If already k, print 0

If parity mismatch or k exceeds sum of both boxes → impossible → -1

Otherwise, adjust by equalizing difference in steps of 2 to reach k.

🧠 Time Complexity: O(1) per test case

📦 Space Complexity: O(1)

---

🧩 **Problem 3: Ordered Distances Check (ORDDIST)**  
🔗 [Link to Problem](https://www.codechef.com/problems/ORDDIST)

🚩 Difficulty: Intermediate

📝 **Problem Statement (Short Summary)**  
Given arrays x and y both of size n,
check if y can be formed by ordering elements based on pairwise distances from some element in x.
Specifically, find an index i such that sorting all elements in x by absolute distance from x[i] results in the sequence y.
If such an index exists, print i + 1. Otherwise, print -1.

✅ **My Code**
```python

def result(n, x, y):
  for i in range(n):
    p = x[i]
    l = sorted((abs(x[j] - p), x[j]) for j in range(n))
    resY = [val for _, val in l]
    if resY == y:
      return i + 1
  return -1

t = int(input())
for _ in range(t):
  n = int(input())
  x = list(map(int, input().split()))
  y = list(map(int, input().split()))
  print(result(n, x, y))



```
💡 **Explanation**

For each index i in x, compute (distance, value) pairs for all x[j] relative to x[i]

Sort these pairs

Extract the values in sorted order and compare to y

If match, return i + 1 (1‑based index), else -1.

🧠 Time Complexity: O(n² log n) in worst case (sorting per index)

📦 Space Complexity: O(n)

---


