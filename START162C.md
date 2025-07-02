🚀 CodeChef Weekly Upload – Starters 162 Division 3  
🗓️ Date: 17 April 2024  
📁 Contest: Starters 162 Division 3  
🎯 Difficulty: Beginner  
👨‍💻 Language: Python  

---

🧩 **Problem 1: Assign Score (ASSIGNSCORE)**  
🔗 [Link to Problem](https://www.codechef.com/problems/ASSIGNSCORE)  
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
You are given marks for `n` questions.  
Each question carries a maximum of 100 marks.  
To pass, the total score should be at least `50%` of the total possible marks.  
Find the minimum score required in the extra question to pass.  
If it's already enough, print `0`. If it's impossible even with full marks, print `-1`.

✅ **My Code**
```python
t = int(input())
for _ in range(t):
  n = int(input())
  a = list(map(int, input().split()))
  k = int(((n + 1) * 100) * 0.5)
  l = sum(a)
  if l >= k:
    print(0)
  else:
    if (k - l) > 100:
      print(-1)
    else:
      print(k - l)
```

💡 **Explanation**

Total possible marks after one extra question: (n + 1) * 100

Required to pass: 50% of total = k

If current total l ≥ k, no need → print 0

Else, check if the remaining needed is ≤ 100 (the extra question’s max score)

If yes → print the required marks

If not → impossible → print -1

🧠 Time Complexity: O(n) per test case
📦 Space Complexity: O(1)


