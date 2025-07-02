🚀 CodeChef Weekly Upload – Starters 163 Division 3  
🗓️ Date: 24 April 2024  
📁 Contest: Starters 163 Division 3  
🎯 Difficulty: Beginner to Intermediate  
👨‍💻 Language: Python  

---

🧩 **Problem 1: Binary String Sum (BINARYSUM)**  
🔗 [Link to Problem](https://www.codechef.com/problems/BINARYSUM)  
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
You are given two integers `n` and `k`.  
Determine if `k` lies within the valid range of binary sum positions, i.e.,  
`n//2 ≤ k ≤ (n+1)//2`.

✅ **My Code**
```python
t = int(input())
for _ in range(t):
  n, k = map(int, input().split())
  if (n // 2) <= k <= (n + 1) // 2:
    print("YES")
  else:
    print("NO")
```
💡 **Explanation**

The binary sum range for valid bit flips is between n//2 and (n+1)//2

Check if k lies within that range and print result accordingly

🧠 Time Complexity: O(1) per test case
📦 Space Complexity: O(1)

---
🧩 **Problem 2: Minimum Items to Buy (MINBUY)**  
🔗[ [Link to Problem]](https://www.codechef.com/problems/MINBUY)
🚩  Difficulty: Intermediate

📝 **Problem Statement (Short Summary)**  
You are given two arrays:

a[i] = quantity of item i

b[i] = price per unit of item i
You need to buy items such that the total cost is at least x.
Find the minimum number of items you must buy to meet or exceed cost x.

✅ **My Code**
```python
t = int(input())
for _ in range(t):
  n, x = map(int, input().split())
  a = list(map(int, input().split()))
  b = list(map(int, input().split()))
  s = []
  for i in range(n):
    s.append(a[i] * b[i])
  if sum(s) < x:
    print(-1)
  else:
    s.sort()
    k = i = 0
    while k < x:
      k += s[n - i - 1]
      i += 1
    print(i)

```
💡 **Explanation**

Multiply quantities and prices to get cost of each item → store in list s

If total cost is less than x, impossible → print -1

Else, sort s in increasing order

Pick largest costs first and accumulate until you reach at least x

Return the minimum number of items needed

🧠 Time Complexity: O(n log n) per test case (due to sorting)
📦 Space Complexity: O(n)
