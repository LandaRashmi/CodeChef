🚀 CodeChef Weekly Upload – Starters 192 Division 3  
🗓️ Date: 25 June 2025  
📁 Contest: Starters 192 Division 3  
🎯 Difficulty: Intermediate to Advanced  
👨‍💻 Language: Python  

🌟 Milestone Unlocked:  
🎉 Reached **3★ (Three-Star)** rating on CodeChef in this round!

---

🧩 **Problem 1: No Odd Sum (NODDSM)**  
🔗 [Link to Problem](https://www.codechef.com/problems/NODDSM)  
🚩 Difficulty: Intermediate  

📝 **Problem Statement (Short Summary)**  
You are given a list of 1s and 2s. You can convert two 1s into a 2 or one 2 into two 1s.  
The goal is to make either 1s or 2s **completely disappear** in the minimum number of operations.

✅ **My Code**
```python
from collections import deque

def key(a, b):
    return (a << 10) | b  

t = int(input())
for _ in range(t):
    n = int(input())
    a = list(map(int, input().split()))
    o = a.count(1)
    t2 = a.count(2)

    q = deque()
    d = {}

    q.append((o, t2))
    d[key(o, t2)] = 0
    ans = 0

    while q:
        a1, a2 = q.popleft()
        dist = d[key(a1, a2)]

        if a1 == 0 or a2 == 0:
            ans = dist
            break

        if a2 > 0:
            na1, na2 = a1 + 2, a2 - 1
            k = key(na1, na2)
            if k not in d:
                d[k] = dist + 1
                q.append((na1, na2))

        if a1 >= 2:
            na1, na2 = a1 - 2, a2 + 1
            k = key(na1, na2)
            if k not in d:
                d[k] = dist + 1
                q.append((na1, na2))

    print(ans)
```
💡 **Explanation**  
Use BFS to simulate all valid transformations

Stop when one of the types (1 or 2) becomes 0

Bitmasking for fast state storage

🧠 Time Complexity: O(states) ≈ O(1000)  
📦 Space Complexity: O(states)


---


🧩 **Problem 2: Secret Line (SECLN)**  
🔗 [Link to Problem ](https://www.codechef.com/problems/SECLN)   
🚩 Difficulty: Intermediate, Easy    

📝 **Problem Statement (Short Summary)**  
Given an array, for each position j, calculate max(a[j] + 1, j). Find the minimum of these values.

✅ **My Code**  
```python

t = int(input())
for _ in range(t):
    n = int(input())
    a = list(map(int, input().split()))
    r = a[0]
    for j in range(n):
        k = max(a[j] + 1, j)
        r = min(r, k)
    print(r)



```
💡 **Explanation**  

For each index, compute the activation time

Return the minimum such value across all indices

🧠 Time Complexity: O(n)  
📦 Space Complexity: O(1)

---



🧩 **Problem 3: No Triple Zero (NO3P)**  
🔗 [Link to Problem](https://www.codechef.com/problems/NO3P)    
🚩 Difficulty: Intermediate  

📝 **Problem Statement (Short Summary)**  
Check whether there exists a rotation such that no prefix or suffix of the array modulo 3 sums to 0.

✅ **My Code**  
```python

t = int(input())
for _ in range(t):
    n = int(input())
    a = list(map(int, input().split()))
    p = [0] * (n + 1)
    for i in range(1, n + 1):
        p[i] = (p[i - 1] + a[i - 1]) % 3
    c1 = c2 = 0
    for i in range(1, n + 1):
        if p[i] == 1 and not c1:
            c1 = i
        if p[i] == 2 and not c2:
            c2 = i
    c = [0]
    if c1: c.append(c1)
    if c2: c.append(c2)
    ok = 0
    for k in c:
        cur = 0
        bad = 0
        for i in range(k):
            cur = (cur + a[k - i - 1]) % 3
            if cur == 0:
                bad = 1
                break
        if bad: continue
        for i in range(k, n):
            cur = (cur + a[i]) % 3
            if cur == 0:
                bad = 1
                break
        if not bad:
            ok = 1
            break
    print("Yes" if ok else "No")



```
💡 **Explanation**  

Precompute prefix sums mod 3

Try rotating the array where prefix mod sum ≠ 0

Check prefix & suffix for mod 3 = 0 condition

🧠 Time Complexity: O(n)  
📦 Space Complexity: O(n)

---


🧩 **Problem 4: Equalize XY (EQXY)**  
🔗 [Link to Problem](https://www.codechef.com/problems/EQXY)    
🚩 Difficulty: Advanced  

📝 **Problem Statement (Short Summary)**  
You are allowed to transform a number using a value z and pay cost c per operation. Make GCD(x, z) equal to LCM(y, z) using the minimum cost.

✅ **My Code**  
```python

import math

def g(x):
    s = set()
    for i in range(1, int(x ** 0.5) + 1):
        if x % i == 0:
            s.add(i)
            s.add(x // i)
    return s

t = int(input())
for _ in range(t):
    x, y, z, c = map(int, input().split())
    if x == y:
        print(0)
        continue

    a = float('inf')

    a1 = math.gcd(x, z)
    b1 = y * z // math.gcd(y, z)
    if a1 == b1:
        a = min(a, c)
    else:
        a2 = a1 * z // math.gcd(a1, z)
        b2 = math.gcd(b1, z)
        if a2 == b2:
            a = min(a, 2 * c)

    a1 = x * z // math.gcd(x, z)
    b1 = math.gcd(y, z)
    if a1 == b1:
        a = min(a, c)
    else:
        a2 = math.gcd(a1, z)
        b2 = b1 * z // math.gcd(b1, z)
        if a2 == b2:
            a = min(a, 2 * c)

    for v in g(x):
        co = abs(z - v) + c
        a1 = math.gcd(x, v)
        b1 = y * v // math.gcd(y, v)
        if a1 == b1:
            a = min(a, co)

    for v in g(y):
        co = abs(z - v) + c
        a1 = x * v // math.gcd(x, v)
        b1 = math.gcd(y, v)
        if a1 == b1:
            a = min(a, co)

    print(a)



```
💡 **Explanation**  

Try all transformations of z to align GCD(x, z) with LCM(y, z)

Test divisors of x and y for optimal z

Keep track of cost

🧠 Time Complexity: O(√x + √y)  
📦 Space Complexity: O(√x + √y)

---

