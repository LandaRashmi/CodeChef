🚀 CodeChef Weekly Upload – Starters 161 Division 3  
🗓️ Date: 20 November 2024  
📁 Contest: Starters 161 Division 3  
🎯 Difficulty: Beginner to Intermediate  
👨‍💻 Language: Python  

---

🧩 **Problem 1: Donut Seller (DONUTSELL)**  
🔗 [Link to Problem](https://www.codechef.com/problems/DONUTSELL)  
🚩 Difficulty: Beginner  

📝 **Problem Statement (Short Summary)**  
There are `n` types of donuts and `m` customers.  
Each customer wants a donut of a particular type.  
If a donut of the requested type is available, it's sold; otherwise, the customer is sad.  
Find the number of sad customers.

✅ **My Code**
```python
def sad_customers(n, a, m, b):
  sad = 0
  for x in b:
    if a[x - 1] > 0:
      a[x - 1] -= 1
    else:
      sad += 1
  return sad

t = int(input())
for _ in range(t):
  n, m = map(int, input().split())
  a = list(map(int, input().split()))
  b = list(map(int, input().split()))
  print(sad_customers(n, a, m, b))
```

💡 **Explanation**

a[i] = available quantity of donut type i+1

For each customer request b[j], check if donut type b[j] is available

If available → sell and decrement stock

If not → increment sad customer count

🧠 Time Complexity: O(m) per test case
📦 Space Complexity: O(1)

---

🧩 **Problem 2: Two Card Game (TWOCARD)**  
🔗 [[Link to Problem] ](https://www.codechef.com/problems/TWOCARD) 

🚩 Difficulty: Intermediate

📝 **Problem Statement (Short Summary)**  
You are given two arrays a and b of size n representing values on each player's card.
A player can choose a card and face either a[i] or b[i] side up.
Determine if the player can choose the best two cards and still lose.
✅ **My Code**
```python
def win(n, a, b):
  ma = -1
  sma = -1
  mi = -1
  smi = -1
  for i in range(n):
    if a[i] > ma:
      sma = ma
      smi = mi
      ma = a[i]
      mi = i
    elif a[i] > sma:
      sma = a[i]
      smi = i
  if mi != -1 and smi != -1:
    if max(b[mi], a[mi]) > max(b[smi], a[smi]):
      print("Yes")
      return
  for i in range(n):
    if i != mi:
      if max(b[i], a[i]) > max(b[mi], a[mi]):
        print("Yes")
        return
  print("No")

t = int(input())
for _ in range(t):
  n = int(input())
  a = list(map(int, input().split()))
  b = list(map(int, input().split()))
  win(n, a, b)

```

💡 **Explanation**

Find the largest (ma) and second largest (sma) values in array a and their indices

Compare the max possible value from a[i] or b[i] at those positions

If the second-best card can beat the best one in terms of face-up value → print Yes

Else, check all other cards to see if any can beat the current best

If so → print Yes, else → No

🧠 Time Complexity: O(n) per test case
📦 Space Complexity: O(1)
