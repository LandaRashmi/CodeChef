🚀 CodeChef Weekly Upload – Starters 159 Division 4  
🗓️ Date: 27 March 2024  
📁 Contest: Starters 159 Division 4  
🎯 Difficulty: Beginner to Intermediate  
👨‍💻 Language: Python  

---

🧩 **Problem 1: Ice Cream Cones (ICECONE)**  
🔗 [Link to Problem](https://www.codechef.com/problems/ICECONE) 
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
You have `x` ice cream cones and `y` friends. You can give one cone to each friend.  
Print the maximum number of cones you can distribute.

✅ **My Code**
```python
x, y = map(int, input().split())
print(min(x, y))
```

💡 **Explanation**

You can give at most one cone to each friend.

The result is the minimum of x and y.

🧠 Time Complexity: O(1)
📦 Space Complexity: O(1)



---

🧩 **Problem 2: Card Game 1 (CARDGAME1)**  
🔗 [[Link to Problem]](https://www.codechef.com/problems/CARDGAME1) 
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
You have n cards and a number x.
Find the maximum number of cards you can pick such that their total sum is odd.
✅ **My Code**
```python
x, y = map(int, input().split())
print(min(x, y))t = int(input())
for _ in range(t):
  n, x = map(int, input().split())
  if x % 2 == 0:
    print((n // 2) - 1)
  else:
    if n % 2 == 0:
      print((n // 2) - 1)
    else:
      print(n // 2)

```
**💡Explanation**

If x is even, avoid ending up with an even sum.

Use count logic depending on parity of n and x.

🧠 Time Complexity: O(t)
📦 Space Complexity: O(1)

---


🧩 **Problem 3: Useless Electricity (USELEC)**  
🔗 [Link to Problem ](https://www.codechef.com/problems/USELEC)
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
You are given two lists a and b representing initial and final charges.
You can increase charge using a battery with z total energy.
Determine if more than half of the appliances can be fully charged.

✅ **My Code**
```python
def f(y, z, a, b):
    c = sum(1 for p, q in zip(a, b) if p > q)
    d = sorted(q - p + 1 for p, q in zip(a, b) if p <= q)
    e = (y // 2) + 1
    for v in d:
        if c >= e:
            print("YES")
            return
        if z >= v:
            z -= v
            c += 1
        else:
            break
    print("YES" if c >= e else "NO")

t = int(input().strip())
for _ in range(t):
    y, z = map(int, input().strip().split())
    a = list(map(int, input().strip().split()))
    b = list(map(int, input().strip().split()))
    f(y, z, a, b)

```
**💡Explanation**

For each device, check if it is already fully charged.

For others, sort by the cost of charging and spend battery power wisely to charge as many as needed.

Goal: charge at least (y // 2) + 1 devices.

🧠 Time Complexity: O(n log n) per test case
📦 Space Complexity: O(n)



---


🧩 **Problem 4: Random Nim (RANDOM_NIM)**  
🔗 [[Link to Problem](https://www.codechef.com/problems/RANDOM_NIM)] 
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
You're playing a variant of Nim. Given n piles with s[i] stones and dice size d,
calculate the probability of winning the game using expected value and modular inverse.

✅ **My Code**
```python
m = 10**9 + 7

def mi(x, m):
  return pow(x, m - 2, m)

def cal(d):
  q = d * d
  p = (d * (d + 1)) // 2
  return p, q

def sel(n, d, s):
  ns = 0
  for c in s:
    ns ^= c
  p, q = cal(d)
  if ns == 0:
    p = q - p
  p %= m
  q %= m
  return (p * mi(q, m)) % m

t = int(input().strip())
for _ in range(t):
  n, d = map(int, input().strip().split())
  s = list(map(int, input().strip().split()))
  print(sel(n, d, s))

```
**💡Explanation**

Uses modular inverse to handle division in modulo arithmetic.

XOR of all piles determines win/loss.

Computes favorable cases using expected probability logic based on dice rolls.

🧠 Time Complexity: O(n) per test case
📦 Space Complexity: O(1)



---

Hope to become 2* by next week ✅
