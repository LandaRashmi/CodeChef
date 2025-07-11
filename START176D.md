🚀 CodeChef Weekly Upload – Starters 176 Division 4  
🗓️ Date: 5 March 2025   
📁 Contest: Starters 176 Division 4  
🎯 Difficulty: Beginner to Intermediate  
👨‍💻 Language: Python  

📈 **Note:**  
Solved **three problems** this time — excellent progress! Slowly working back toward improving my rating above **1★**.

---

🧩 **Problem 1: Relative Urgency (RURT)**  
🔗 [Link to Problem](https://www.codechef.com/problems/RURT)  
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
You are given two values `x` and `y`. Find how many full units of `x` can fit in `y`, **excluding exact fits**.

✅ **My Code**
```python
x, y = map(int, input().split())
k = (y // x) - (1 if y % x == 0 else 0)
print(max(k, 0))
```
💡 **Explanation**

If y is perfectly divisible by x, subtract 1

Otherwise, use floor division

Ensure the result isn't negative using max(k, 0)

🧠 Time Complexity: O(1)

📦 Space Complexity: O(1)

---

🧩 **Problem 2: Maximize Happiness (XLSL)**  
🔗 [Link to Problem](https://www.codechef.com/problems/XLSL)

🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
Match pairs of small (S), large (L), and extra large (XL) shirts with people requesting them.
Use fallback matching rules to maximize the number of happy people.

✅ **My Code**
```python
def max_happy(X, Y, Z, A, B, C):
  happy = 0
  s = min(X, A)
  happy += s
  X -= s
  A -= s
  
  l = min(Y, B)
  happy += l
  Y -= l
  B -= l 

  xl = min(Z, C)
  happy += xl
  Z -= xl
  C -= xl

  xl_to_l = min(Z, B)
  happy += xl_to_l
  Z -= xl_to_l
  B -= xl_to_l

  xl_to_s = min(Z, A)
  happy += xl_to_s
  Z -= xl_to_s
  A -= xl_to_s

  l_to_s = min(Y, A)
  happy += l_to_s
  Y -= l_to_s
  A -= l_to_s

  return happy

T = int(input().strip())
for _ in range(T):
  X, Y, Z, A, B, C = map(int, input().split())
  print(max_happy(X, Y, Z, A, B, C))


```
💡 **Explanation**

Match shirts by direct size first

Then allow fallback matching in order: XL → L, XL → S, L → S

Greedy approach to maximize satisfied customers

🧠 Time Complexity: O(1) per test case

📦 Space Complexity: O(1)

---

🧩 **Problem 3: Love Summit University (LSU)**  
🔗 [Link to Problem](https://www.codechef.com/problems/LSU)
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
You're given a string of characters and must compute a value based on frequency counts and an associated cost c.
You must minimize total cost using a hybrid strategy.

✅ **My Code**
```python

def summit(n, c, s):
  from collections import Counter
  d = Counter(s)
  a = sorted(d.values(), reverse=True)
  u = len(a)

  x = u * c
  y = n * (n + 1) // 2
  m = min(x, y)

  p = [0] * (u + 1)
  for i in range(u):
    p[i + 1] = p[i] + a[i]

  for k in range(1, u + 1):
    m = min(m, k * c + (p[u] - p[k]) * (p[u] - p[k] + 1) // 2)

  return m

t = int(input())
for _ in range(t):
  n, c = map(int, input().split())
  s = input().strip()
  print(summit(n, c, s))


```
💡 **Explanation**

Count frequencies of each character

Try multiple partition points (k) where k groups pay fixed cost c, and the rest form a penalty

Prefix sum optimization used for quick cost calculations

Greedy + prefix approach for efficient result

🧠 Time Complexity: O(n log n) per test case

📦 Space Complexity: O(n)

---
