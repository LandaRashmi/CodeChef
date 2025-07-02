🚀 CodeChef Weekly Upload – Starters 165 Division 4  
🗓️ Date: 8 May 2024  
📁 Contest: Starters 165 Division 4  
🎯 Difficulty: Beginner to Intermediate  
👨‍💻 Language: Python  

---

🧩 **Problem 1: Crack the Exam (CRCK)**  
🔗 [Link to Problem](https://www.codechef.com/problems/CRCK)  
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
Chef needs to answer 25 questions.  
Given `n` questions already solved, print how many more are needed.

✅ **My Code**
```python
n = int(input())
print(25 - n)
```
💡 **Explanation**

Simply subtract the number of questions solved from 25.

🧠 Time Complexity: O(1)
📦 Space Complexity: O(1)

---

🧩 **Problem 2: Post Office Perimeter (POSTPERI)**  
🔗 [[Link to Problem]](https://www.codechef.com/problems/POSTPERI)
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
You are given a post office of n x m size.
You want the closest perimeter (2 * (length + width)) to a target value k.
Print the minimum absolute difference between any possible perimeter and k.

✅ **My Code**
```python
t = int(input())
for _ in range(t):
  n, m, k = map(int, input().split())
  r = float('inf')
  for i in range(1, n + 1):
    for j in range(1, m + 1):
      p = 2 * (i + j)
      r = min(r, abs(k - p))
  print(r)

```
💡 **Explanation**

Try all rectangle sizes from 1x1 to n x m

Compute perimeter and track the smallest difference from k

🧠 Time Complexity: O(n * m) per test case
📦 Space Complexity: O(1)

---

🧩 **Problem 3: Balanced Distribution (BDISC)**  
🔗 [[Link to Problem](https://www.codechef.com/problems/BDISC)]
🚩 Difficulty: Intermediate

📝 **Problem Statement (Short Summary)**  
You're given an array of n numbers.
Rearrange the array such that a[i] ≤ i to minimize total penalties.
Penalty for each a[i] if it's greater than i is a[i] - i.

✅ **My Code**
```python
def solution(n, a):
  a.sort()
  res = 0
  for i in range(n):
    res += max(a[i] - i, 0)
  return res

t = int(input())
for _ in range(t):
  n = int(input())
  a = list(map(int, input().split()))
  print(solution(n, a))

```
💡 **Explanation**

Sort the array to align smaller numbers to lower indices

For each index i, add a[i] - i only if a[i] > i

🧠 Time Complexity: O(n log n) per test case
📦 Space Complexity: O(1)

---
A 2⭐ again
