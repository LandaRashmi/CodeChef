🚀 CodeChef Weekly Upload – Starters 174 Division 4  
🗓️ Date: 19 February 2025  
📁 Contest: Starters 174 Division 4  
🎯 Difficulty: Beginner  
👨‍💻 Language: Python  

📉 **Note:**  
I was able to solve **only one problem** in this contest, so my rating **remains at 1★** on CodeChef.  
Still moving forward with consistency and learning.

---

🧩 **Problem 1: Finish Homework (HWFIN)**  
🔗 [Link to Problem](https://www.codechef.com/problems/HWFIN)  
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
Chef has `x` minutes left in the day and needs to finish homework worth `y` pages.  
Each page takes `10` minutes.  
Determine if Chef can complete the homework before the day ends.

✅ **My Code**
```python
x, y = map(int, input().split())
z = 0
if 100 - x - (y * 10) <= 0:
  print("Yes")
else:
  print("No")
```

**💡 Explanation**

Total available time = 100 - x

Time needed = y * 10

If required time ≤ remaining time, print "Yes", else "No"

🧠 Time Complexity: O(1)
📦 Space Complexity: O(1)
