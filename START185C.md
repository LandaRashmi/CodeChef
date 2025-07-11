🚀 CodeChef Weekly Upload – Starters 185 Division 3 

🗓️ Date: 10 July 2025

📁 Contest: Starters 185 Division 3

🎯 Difficulty Level: Beginner to Intermediate

👨‍💻 Language Used: Python

---

✅ Solved 1 problem and reviewed 2 challenging ones — staying consistent is key to growth!

---
**🧩 Problem 1: Red Blue Lost Their Turn (RBLT)**
🔗 [Link to Problem](https://www.codechef.com/problems/RBLT)

🚩 Difficulty: Beginner

**📝 Problem Summary**

You are given n turns (even number) in a two-player game involving Red (1), Blue (2), and Unknown (0) moves.
Your task is to decide if it’s possible to fill the unknown moves such that both Red and Blue have exactly n/2 turns.

**✅ My Code**
```
python

t = int(input())
for _ in range(t):
  n = int(input())
  c = list(map(int, input().split()))
  r = c.count(1)
  b = c.count(2)
  u = c.count(0)
  if n % 2 != 0:
    print("No")
    continue
  x = n // 2
  nr = x - r
  nb = x - b
  if nr < 0 or nb < 0:
    print("No")
  elif nr + nb == u:
    print("Yes")
  else:
    print("No")
```

**💡 Explanation**

Red and Blue should each have n/2 moves.

If known moves exceed n/2 → invalid.

Remaining required moves must match the count of unknowns (0s).

Time Complexity: O(n) per test case

Space Complexity: O(1)

---
Unsolved Problems
---
**❌ Problem 2: Adjacent Graph (ADJG)**

🔗 [Link to Problem](https://www.codechef.com/problems/ADJG)

🚩 Difficulty: Intermediate

**📝 Problem Summary**

You are given a permutation p of numbers from 1 to n.
Construct an undirected graph with n nodes where an edge between nodes i and j exists if and only if |i - j| = 1.
You need to check if there's a path from p[0] to p[n-1] that visits all the elements in p in the given order.

**💡 Explanation**

Graph is a linear chain: only adjacent nodes are connected.

Problem becomes: Can we follow the permutation p using only steps of +1 or -1?

**🔍 Intuition**

For each consecutive pair in p, check if |p[i] - p[i+1]| == 1.

If any step jumps more than 1, path is not possible.

Time Complexity: O(n)

Space Complexity: O(1)

---

**❌ Problem 3: Creature Hunt (CREAHUN)**
🔗 [Link to Problem](https://www.codechef.com/problems/CREAHUN)

🚩 Difficulty: Intermediate

**📝 Problem Summary**

You are given two arrays:

a: strength of n creatures

b: strength of m bullets

You can use each bullet only once.
A bullet can kill a creature only if bullet strength ≥ creature strength.

Goal: Maximize the number of creatures you can kill.

**💡 Explanation**

Sort both arrays.

Use two pointers: one for creatures and one for bullets.

Greedily match the weakest bullet that can kill the current weakest creature.

**🔍 Intuition**

It's a greedy matching problem.

Always assign the least bullet capable of killing the current creature to maximize remaining options.

Time Complexity: O(n log n + m log m)

Space Complexity: O(1)
