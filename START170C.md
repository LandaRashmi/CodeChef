🚀 CodeChef Weekly Upload – Starters 170 Division 3  
🗓️ Date: 12 June 2024  
📁 Contest: Starters 170 Division 3  
🎯 Difficulty: Beginner to Intermediate  
👨‍💻 Language: Python  

---

🧩 **Problem 1: Minimum Bottles (MINBOTTLES)**  
🔗 [Link to Problem](https://www.codechef.com/problems/MINBOTTLES) 
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
You have `n` bottles containing liquid, and each bottle contains a certain amount.  
Given a container that can hold `x` units, find the **minimum number of containers** needed to store the total liquid from all bottles.


✅ **My Code**
```python
t = int(input())
for _ in range(t):
  n, x = map(int, input().split())
  a = list(map(int, input().split()))
  tot = sum(a)
  b = (tot + x - 1) // x
  print(b)
```
💡 **Explanation**

Calculate the total volume tot = sum(a)

Use ceiling division to get minimum containers needed: (tot + x - 1) // x
(which is equivalent to ceil(tot / x))

🧠 Time Complexity: O(n) per test case
📦 Space Complexity: O(1)

---


🧩 **Problem 2: KO Monster (KO_MON)**  
🔗 [Link to Problem](https://www.codechef.com/problems/KO_MON)
🚩 Difficulty: Intermediate

📝 **Problem Statement (Short Summary)**  
You're given health values of n monsters and a fixed damage x applied each second.
You can fight one monster at a time.
Each second you deal x extra damage to the next monster due to delay.
Find the maximum health value adjusted after delay (i.e., h[i] + i*x) and print it.

✅ **My Code**
```python

t = int(input())
for _ in range(t):
  n, x = map(int, input().split())
  h = list(map(int, input().split()))
  h.sort(reverse=True)
  m = 0
  for i in range(n):
    a = h[i] + i * x
    m = max(m, a)
  print(m)



```
💡 **Explanation**

Sort monsters by health in descending order (to fight stronger ones first)

For each monster at index i, compute adjusted health h[i] + i*x

Track the maximum adjusted value which determines required power/time

🧠 Time Complexity: O(n log n) per test case (due to sorting)
📦 Space Complexity: O(1)

---

