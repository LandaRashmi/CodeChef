# 🚀 CodeChef Weekly Upload – Starters 75 Division 4

🗓️ **Date:** 10 August 2022  
📁 **Contest:** Starters 75 Division 4  
🎯 **Difficulty:** Beginner  
👨‍💻 Language: C

---

## 🧩 Problem 1: Tax Saving (`TAXSAVING`)
🔗 [Link to Problem](https://www.codechef.com/problems/TAXSAVING)  

🚩 Difficulty: Beginner

---

### 📝 Problem Statement (Short Summary)

Chef earns a salary of `x` rupees per month and pays `y` rupees as tax.  
Find the amount he **saves** every month.

---

### ✅ My Code

```c
#include <stdio.h>

int main(void) {
    int t,x,y;
    scanf("%d",&t);
    while(t--){
        scanf("%d %d",&x,&y);
        printf("%d\n",x-y);
    }
    return 0;
}
```
## 💡 Explanation
Input the number of test cases t.

For each test:

Read the salary x and tax y.

Compute the saved amount as x - y.

Print the result.

This is a simple arithmetic operation checking net earnings after tax.

🧠 Time Complexity: O(t)
📦 Space Complexity: O(1)

---

## 🧩 Problem 2: Profit Increase (PROINC)
🔗 [Link to Problem](https://www.codechef.com/problems/PROINC)
🚩 Difficulty: Beginner

### 📝 Problem Statement (Short Summary)
Chef’s business earns a profit of y rupees.
He expects a 10% increase on a base amount x (i.e., (10 * x) / 100).
Calculate the total expected profit.

### ✅ My Code
```c

#include <stdio.h>

int main(void) {
    int t,x,y;
    scanf("%d",&t);
    while(t--){
        scanf("%d %d",&x,&y);
        printf("%d\n",(x*10)/100+y);
    }
    return 0;
}
```
## 💡 Explanation
Read the number of test cases t.

For each test:

Input the base amount x and initial profit y.

Calculate the 10% of x as (x * 10) / 100

Add it to y to get the total expected profit.

Print the final result.

🧠 Time Complexity: O(t)
📦 Space Complexity: O(1)
