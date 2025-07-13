🚀 CodeChef Weekly Upload – Starters 169 Division 3  
🗓️ Date: 15 january 2025   
📁 Contest: Starters 169 Division 3  
🎯 Difficulty: Beginner to Intermediate  
👨‍💻 Language: Python  

---

🧩 **Problem 1: Invert Binary String (P2169)**  
🔗 [Link to Problem](https://www.codechef.com/problems/P2169)  
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
You're given a binary string.  
For each character:
- If it's `1`, turn it into `0`  
- If it's `0`, turn it into `1`  
Print the inverted string.

✅ **My Code**
```python
t = int(input())
for i in range(t):
  n = int(input())
  s = input()
  k = ''
  for i in s:
    if i == '1':
      k += '0'
    else:
      k += '1'
  print(k)
```
💡 **Explanation**

Loop through the string s

Flip each bit and build the new string

Print the result

🧠 Time Complexity: O(n) per test case
📦 Space Complexity: O(n)

---

🧩 **Problem 2: Group Sort by Set Bits (P4169)**  
🔗 [[Link to Problem]](https://www.codechef.com/problems/P4169)
🚩 Difficulty: Intermediate  

📝 **Problem Statement (Short Summary)**  
You are given an array l of n integers.
You must group elements by their number of set bits (1s in binary).
Sort each group internally, and then check if the entire array becomes sorted.
If so, print "Yes", else "No".

✅ **My Code**
```python
def count_set_bits(x):
  c = 0
  while x:
    c += (x & 1)
    x >>= 1
  return c

def can_be_sorted(l):
  b = {}
  for i in range(len(l)):
    s = count_set_bits(l[i])
    if s not in b:
      b[s] = []
    b[s].append(i)
  
  for i in b.values():
    v = [l[j] for j in i]
    v.sort()
    for j, idx in enumerate(i):
      l[idx] = v[j]
  
  for i in range(1, len(l)):
    if l[i] < l[i - 1]:
      return False
  return True

t = int(input())
for _ in range(t):
  n = int(input())
  l = list(map(int, input().split()))
  print("Yes" if can_be_sorted(l) else "No")

```
💡 **Explanation**

Count the number of set bits for each element

Group elements with the same set bit count

Sort each group and reassign values to original indices

Finally, check if the array is non-decreasing

🧠 Time Complexity: O(n log n) due to group-wise sorting
📦 Space Complexity: O(n)

---

