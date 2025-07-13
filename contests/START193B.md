🚀 CodeChef Weekly Upload – Starters 193 Division 3  
🗓️ Date: 2 July 2025  
📁 Contest: Starters 193 Division 3   
👨‍💻 Language: Python  

📈 Note:  
Solved 3 problems in this Division 3 contest! Clean logic and efficient handling of basic number theory and permutations.

---

🧩 **Problem 1: Count Odd and Even Divisors (CNTODDEVEN)**  
🔗 [Link to Problem](https://www.codechef.com/problems/CNTODDEVEN)  
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
Given a number `n`, count how many of its divisors are odd and how many are even.

✅ **My Code**
```python
t = int(input())
for _ in range(t):
    n = int(input())
    o = e = 0
    for i in range(1, n + 1):
        if n % i == 0:
            if i % 2 == 0:
                e += 1
            else:
                o += 1
    print(o, e)
```
💡 **Explanation**  

Loop through all numbers from 1 to n

Check if each is a divisor of n

Increment odd/even counters accordingly

🧠 Time Complexity: O(n)   
📦 Space Complexity: O(1)

---

🧩 **Problem 2: Odd-Even Divisibility (ODDEVENDIV)**  
🔗 [Link to Problem](https://www.codechef.com/problems/ODDEVENDIV)    
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
Given two numbers a and b, check if:

a is ≥ 1

and b is divisible by a

✅ **My Code**  
```python

t = int(input())
for _ in range(t):
    a, b = map(int, input().split())
    if a >= 1 and b % a == 0:
        print("Yes")
    else:
        print("No")



```
💡 **Explanation**  

Check conditions directly with simple if/else

a must not be zero (to avoid division by zero)

b % a == 0 ensures clean divisibility

🧠 Time Complexity: O(1)  
📦 Space Complexity: O(1)

---


🧩 **Problem 3: Add to Permutation (ADDPERM)**  
🔗 [Link to Problem](https://www.codechef.com/problems/ADDPERM)    
🚩 Difficulty: Moderate  

📝 **Problem Statement (Short Summary)**  
Generate a permutation of n numbers such that the sum of the first n-k+1 elements is maximized.

✅ **My Code**  
```python

t = int(input())
for _ in range(t):
    n, k = map(int, input().split())
    m = n - k + 1
    r = [0] * n
    for i in range(1, m + 1):
        r[i - 1] = m + 1 - i
    for i in range(m + 1, n + 1):
        r[i - 1] = i
    print(*r)


```
💡 **Explanation**  

Reverse the first n-k+1 numbers for maximum prefix sum

Keep the rest in increasing order to form a valid permutation

🧠 Time Complexity: O(n)  
📦 Space Complexity: O(n)

---

