🚀 CodeChef Weekly Upload – Starters 160 Division 4  
🗓️ Date: 13 November 2024  
📁 Contest: Starters 160 Division 4  
🎯 Difficulty: Beginner  
👨‍💻 Language: Python  

---

🧩 **Problem 1: Move Problems (MOVPR)**  
🔗 [Link to Problem](https://www.codechef.com/problems/MOVPR)  
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
Chef has `x` easy problems and `y` medium problems to practice.  
He needs to practice at least `z` problems.  
- Each easy problem takes 2 minutes  
- Each medium problem takes 3 minutes  
Find the minimum total time to practice `z` problems.

✅ **My Code**
```python
x, y, z = map(int, input().split())
if x + y >= z:
  print(z * 2 + y)
else:
  print(x * 2 + y * 3)
```
💡 **Explanation**

If x + y ≥ z, Chef can choose z problems from available problems

Minimum time: z * 2 (assuming all easy) + y penalty

Else, use all problems: x * 2 + y * 3

🧠 Time Complexity: O(1)
📦 Space Complexity: O(1)

---


🧩 **Problem 2: Oranges Required (ORANGES)**  
🔗 [Link to Problem ](https://www.codechef.com/problems/ORANGES)
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
A pack of n oranges should contain between 10n and 12n oranges.
Given k oranges in a pack, check whether it is valid or not.

✅ **My Code**
```python
t = int(input())
for _ in range(t):
  n, k = map(int, input().split())
  if k < n * 10 or k > n * 12:
    print("NO")
  else:
    print("YES")

```
💡 **Explanation**

Check if k lies within the inclusive range [10*n, 12*n]

If yes → valid pack → print YES

Else → invalid → print NO

🧠 Time Complexity: O(t)
📦 Space Complexity: O(1)

---


🧩 **Problem 3: Buy Orders Easy (BUYORDEREZ)**  
🔗 [[Link to Problem] ](https://www.codechef.com/problems/BUYORDEREZ)
🚩 Difficulty: Intermediate

📝 **Problem Statement (Short Summary)**  
You're given a list b of size n with values 0 or 1, representing buy orders.
Calculate a specific metric involving:

Sum of first n-1 elements

Count of zeros from index 1 to n-1

Combine to return a special result

✅ **My Code**
```python
def cal(n, b):
  x = sum(b[0:n-1])
  y = sum(1 for i in range(1, n) if b[i] == 0)
  r = min(x + y, n - 1)
  return r + n

T = int(input())
for _ in range(T):
  n = int(input())
  b = list(map(int, input().split()))
  print(cal(n, b))

```
💡 **Explanation**

x = sum of first n-1 elements

y = number of zeros from index 1 to n-1

Result: min(x + y, n - 1) + n

This handles some bounded operation related to orders and penalties

🧠 Time Complexity: O(n) per test case
📦 Space Complexity: O(1)

----

I'm a 2⭐ coder now 🥳🎊🎉
