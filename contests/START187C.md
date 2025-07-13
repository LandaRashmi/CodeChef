🚀 CodeChef Weekly Upload – Starters 187 Division 3  
🗓️ Date: 21 May 2025  
📁 Contest: Starters 187 Division 3  
🎯 Difficulty: Intermediate  
👨‍💻 Language: Python  

📈 Note:  
I attempted 2 problems in this contest. One was solved successfully, and the other required recursive game logic — a great learning experience!

---

🧩 **Problem 1: Chocolate Cut (CHOCUT)**  
🔗 [Link to Problem](https://www.codechef.com/problems/CHOCUT)  
🚩 Difficulty: Intermediate  

📝 **Problem Statement (Short Summary)**  
You're given a chocolate of size `n × m` and an integer `k`.  
You can make a **single straight cut** (horizontal or vertical), resulting in two parts.  
Find the **maximum possible area** of the remaining piece, given that one piece must have area at least `k`.  
If it's not possible to make such a cut, output `0`.  
If `k == 0`, the answer is the total area.

✅ **My Code**
```python
t = int(input())
for _ in range(t):
  n, m, k = map(int, input().split())
  total = n * m
  res = 0 if k > total else total if k == 0 else 0

  for i in range(1, n):
    a = i * m
    b = (n - i) * m
    if a >= k:
      res = max(res, b)
    if b >= k:
      res = max(res, a)

  for j in range(1, m):
    a = j * n
    b = (m - j) * n
    if a >= k:
      res = max(res, b)
    if b >= k:
      res = max(res, a)

  print(res)

```
💡 **Explanation**  

Try all possible horizontal and vertical cuts

For each cut, calculate both areas

Keep the maximum valid area where the other piece is ≥ k

If k > n * m, no cut is valid → return 0

🧠 Time Complexity: O(n + m)  
📦 Space Complexity: O(1)

---

🧩 **Problem 2: Increasing Game (INCGAME)**  
🔗 [Link to Problem](https://www.codechef.com/problems/INCGAME)  
🚩 Difficulty: Intermediate   

📝 **Problem Statement (Short Summary)**  
Two players (Alice and Bob) play a game with piles of size x and y.
They take turns removing any number i of stones (starting from 1 to k) in increasing order, i.e., each move must use a larger value than the previous.
Who will win if both play optimally?

✅ **My Code**  
```python

t = int(input())

def w(x, y, p, k, f):
  l = k if f else max(x, y)
  for i in range(p + 1, l + 1):
    if i <= x and not w(x - i, y, i, k, False):
      return True
    if i <= y and not w(x, y - i, i, k, False):
      return True
  return False

for _ in range(t):
  x, y, k = map(int, input().split())
  print("Alice" if w(x, y, 0, k, True) else "Bob")


```
💡 **Explanation**  

Use recursive game simulation

Track the previous move value to ensure strictly increasing choices

If current player can force a win by any valid move → they win

Base case: No move left = lose

🧠 Time Complexity: Exponential (due to recursion, can be improved using memoization)  
📦 Space Complexity: Depends on recursion depth (up to O(k))

---


