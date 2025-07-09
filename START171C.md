🚀 CodeChef Weekly Upload – Starters 171 Division 3  
🗓️ Date: 19 June 2024  
📁 Contest: Starters 171 Division 3  
🎯 Difficulty: Beginner to Intermediate  
👨‍💻 Language: Python  

---

🧩 **Problem 1: Advitiya Cipher (ADVITIYA)**  
🔗 [Link to Problem](https://www.codechef.com/problems/ADVITIYA)  
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
You are given a string `s` of length 8.  
Find the **minimum number of alphabetic shifts (circular)** required to convert it into the word `"ADVITIYA"`.  
Each character can wrap around using modulo-26 behavior (like a Caesar cipher).

✅ **My Code**
```python
t = int(input())
k = "ADVITIYA"
for _ in range(t):
  s = input().strip()
  res = 0
  for i, j in zip(s, k):
    if i <= j:
      x = abs(ord(i) - ord(j))
    else:
      x = 26 - abs(ord(i) - ord(j))
    res += x
  print(res)
```

💡 **Explanation**

For each character in s, compare with the corresponding character in "ADVITIYA"

Calculate the minimum circular shift needed using modular alphabet rotation

Sum the shifts for all characters

🧠 Time Complexity: O(1) per test case (fixed string length = 8)
📦 Space Complexity: O(1)

---



🧩 **Problem 2: Swish Game (SWISHGAME)**  
🔗 [Link to Problem](https://www.codechef.com/problems/SWISHGAME)
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
You are given a string s consisting of characters 'S' and 'P'
Each 'S' counts as a shot made.
Given a target score k, determine the minimum number of players required to complete the score.

✅ **My Code**
```python
t = int(input())
for _ in range(t):
  m, k = map(int, input().split())
  s = input()
  p = s.count('S')
  if p >= k:
    print(m)
  else:
    n = k - p
    print(m + n - 1)


```
💡 **Explanation**

m is the number of current players

Count how many shots 'S' are already there in the input string

If enough, no need to add players

Otherwise, compute the shortfall and add players to meet the required score

One player can shoot once in their turn, so you add (k - p) extra shots using (k - p) new turns, hence (m + (k - p) - 1)

🧠 Time Complexity: O(n) per test case
📦 Space Complexity: O(1)

---


