# 🚀 CodeChef Weekly Upload – Starters 71D

🗓️ **Date:** 15 June 2022  
📁 **Contest:** Starters 71 Division 2  
🎯 **Difficulty:** Beginner  
👨‍💻 **Language:** C

---

## 🧩 Problem 1: Instagram Followers (`INSTAGRAM`)
🔗 [Link to Problem](https://www.codechef.com/problems/INSTAGRAM)  
🚩 Difficulty: Beginner

---

### 📝 Problem Statement (Short Summary)

Chef has `x` followers and is following `y` people on Instagram.  
To be considered "popular", Chef must have **more than 10 times** the number of people he is following.  
Print **YES** if Chef is popular, otherwise print **NO**.

---

### ✅ My Code

```c
#include <stdio.h>

int main(void) {
    int t,x,y;
    scanf("%d",&t);
    while(t--)
    {
        scanf("%d %d",&x,&y);
        if(x>y*10)
        {
            printf("YES\n");
        }
        else
        {
            printf("NO\n");
        }
    }
    return 0;
}
```
## 💡 Explanation
We read the number of test cases t.

For each test case, input x (followers) and y (following).

Check if x > 10 * y:

If true, Chef is popular, print YES.

Otherwise, print NO.

🧠 Time Complexity: O(t)
📦 Space Complexity: O(1)

---


## 🧩 Problem 2: Perfect Trio (PERFECTTRIO)
🔗 [Link to Problem](https://www.codechef.com/problems/PERFECTTRIO))  
🚩 Difficulty: Beginner

## 📝 Problem Statement (Short Summary)
Given three integers a, b, and c, determine whether any one of them is the sum of the other two.
Print YES if such a condition exists, otherwise print NO.

## ✅ My Code
```c

#include <stdio.h>

int main(void) {
    int t,a,b,c;
    scanf("%d",&t);
    while(t--)
    {
        scanf("%d %d %d",&a,&b,&c);
        if(a==b+c)
        {
            printf("YES\n");
        }
        else if(b==a+c)
        {
            printf("YES\n");
        }
        else if(c==a+b)
        {
            printf("YES\n");
        }
        else
        {
            printf("NO\n");
        }
    }
    return 0;
}
```
## 💡 Explanation
We read the number of test cases t.

For each test case, input three integers: a, b, c.

Check the three conditions:

a == b + c

b == a + c

c == a + b

If any condition is true, output YES; otherwise, output NO.

🧠 Time Complexity: O(t)
📦 Space Complexity: O(1)
