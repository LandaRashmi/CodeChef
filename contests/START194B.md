🚀 CodeChef Weekly Upload – Starters 194 Division 3  
🗓️ Date: 13 July 2025  
📁 Contest: Starters 194 Division 3  
🎯 Difficulty: Intermediate  
👨‍💻 Language: Python  

📈 Note:  
Solved three problems this round! Good mix of brute force optimization, greedy selection, and matrix-based logic.

---

🧩 **Problem 1: Bake the Cake (BAKECAKE3)**  
🔗 [Link to Problem](https://www.codechef.com/problems/BAKECAKE3)  
🚩 Difficulty: Intermediate  

📝 **Problem Statement (Short Summary)**  
You’re given `n` cakes with sweetness levels. You can **cap** the sweetness at any level `x` (0 ≤ x ≤ 100) and get 50 coins per capped unit of sweetness. However, it costs 30 coins per cake per unit `x`. Maximize your total profit.

✅ **My Code**
```python
t = int(input())
for _ in range(t):
    n = int(input())
    a = list(map(int, input().split()))
    ans = 0
    for x in range(0, 101):
        s = 0
        for i in a:
            s += min(x, i)
        p = s * 50 - x * 30 * n
        ans = max(ans, p)
    print(ans)
```
💡 **Explanation**  

Brute-force all values from 0 to 100 for the cap x

Compute total capped sweetness and subtract cost

Track the maximum possible profit

🧠 Time Complexity: O(100 * n)  
📦 Space Complexity: O(1)

---


🧩 **Problem 2: Mark All (MARKALL)**  
🔗 [Link to Problem](https://www.codechef.com/problems/MARKALL)    
🚩 Difficulty: Intermediate  

📝 **Problem Statement (Short Summary)**   

Given an array, find the minimum of the first and last elements or the sum of two smallest elements — whichever is smaller.

✅ **My Code**  
```python

t = int(input())
for _ in range(t):
    n = int(input())
    a = list(map(int, input().split()))
    f = min(a[0], a[-1])
    x, y = a[0], a[1]
    if x > y:
        x, y = y, x
    for v in a[2:]:
        if v < x:
            y = x
            x = v
        elif v < y:
            y = v
    print(min(f, x + y))



```
💡 **Explanation**  

Keep track of first and last elements

Find two smallest numbers

Output the minimum between those two strategies

🧠 Time Complexity: O(n)  
📦 Space Complexity: O(1)

---


🧩 **Problem 3: Count Good Arrays (CNTGOODARR)**  
🔗 [Link to Problem](https://www.codechef.com/problems/CNTGOODARR)    
🚩 Difficulty: Intermediate  

📝 **Problem Statement (Short Summary)**  

You’re given a binary matrix.

Define A = product of 1s count in each row

Define B = product of 1s count in paired rows (top–bottom halves) where both have 1s in same column
Print (A - B + MOD) % MOD where MOD = 10^9 + 7

✅ **My Code**  
```python

mod = 10**9 + 7
t = int(input())
for _ in range(t):
    n = int(input())
    m = [input().strip() for _ in range(n)]
    a = 1
    for r in m:
        c = r.count('1')
        a = a * c % mod
    h = n // 2
    b = 1
    for i in range(h):
        c = 0
        r1 = m[i]
        r2 = m[i + h]
        for j in range(n):
            if r1[j] == '1' and r2[j] == '1':
                c += 1
        b = b * c % mod
    print((a - b + mod) % mod)



```
💡 **Explanation**  

For each row, count 1s and multiply into A

For paired rows (top with bottom), count overlapping 1s and multiply into B

Final result is A - B under modulo

🧠 Time Complexity: O(n²)  
📦 Space Complexity: O(n)

---

