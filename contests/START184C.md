🚀 CodeChef Weekly Upload – Starters 184 Division 3  
🗓️ Date: 30 April 2025  
📁 Contest: Starters 184 Division 3  
🎯 Difficulty: Beginner to Intermediate  
👨‍💻 Language: Python  

📈 **Note:**  
Solved **two problems** in this contest — steady progress and still maintaining my **2★** rating!

---

🧩 **Problem 1: Zero Sum Array (SUM0)**  
🔗 [Link to Problem](https://www.codechef.com/problems/SUM0)  
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
Create an array of size `n` such that its elements sum to zero.  
If `n == 1`, it's impossible (print `-1`).  
Otherwise:
- For even `n`: alternate `1, -1`.
- For odd `n`: start with `[1, 2, -3]`, then fill the rest with alternating pairs.

✅ **My Code**
```python
t = int(input())
for _ in range(t):
  n = int(input())
  if n == 1:
    print(-1)
  else:
    if n % 2 == 0:
      a = [1, -1] * (n // 2)
    else:
      a = [1, 2, -3]
      k = n - 3
      a += [1, -1] * (k // 2)
    print(*a)
```
💡 **Explanation**
For even n, we pair +1 and -1 to get zero-sum.

For odd n ≥ 3, we start with [1, 2, -3] which sums to 0 and add more 1, -1 pairs.

If n == 1, it's impossible to construct such an array, so print -1.

🧠 Time Complexity:

O(n) per test case for generating and printing the array.

Overall: O(t * n) for t test cases.

📦 Space Complexity:

O(n) space per test case for storing the result array.

---

🧩 **Problem 2: First Step Equality (FSTS)**  
🔗 [Link to Problem](https://www.codechef.com/problems/FSTS)  
🚩 Difficulty: Intermediate  

📝 **Problem Statement (Short Summary)**  
You have two binary strings s and u of the same length.
The goal is to determine whether it's possible to transform s into u using a defined operation, under constraints:

1. s should not have a 0 at any position where u has 1.

2. The parity of the number of '1' characters in both strings should match (i.e., difference is even).

✅ **My Code**
```python

t = int(input())
for _ in range(t):
  n = int(input())
  s = input().strip()
  u = input().strip()
  ok = True
  for x, y in zip(s, u):
    if x == '0' and y == '1':
      ok = False
      break
  
  if not ok:
    print("No")
    continue
  
  cnts = s.count('1')
  cntu = u.count('1')
  print("Yes" if (cnts - cntu) % 2 == 0 else "No")



```
💡 **Explanation**
Invalid Case: If s[i] = '0' and u[i] = '1', it's impossible, so print "No".

Valid Case: If you can only flip 1 → 0, then the number of 1s in s must be enough to cover 1s in u.

Additional constraint: (count of 1s in s) - (count in u) should be even.
This reflects a parity-based operation constraint.

🧠 Time Complexity:

O(n) per test case for string comparison and count operations.

Overall: O(t * n) for t test cases.

📦 Space Complexity:

O(1) auxiliary space — constant extra space used regardless of input size.

---


---

Is it only me? but i feel like the difficulty has increased a little...because i couldn't solve the 3rd question even though i tried many times
