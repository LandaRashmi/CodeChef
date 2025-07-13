# 🧩 Problem: Rain Category (`RAINFALL1`)
🔗 [Link to Problem](https://www.codechef.com/START69D/problems/RAINFALL1)

- 📅 **Contest:** Starters 69 Division 2  
- 📆 **Date:** 1 June 2022  
- 🚩 **Difficulty:** Beginner

---

## 📝 Problem Statement (Short Summary)

Given the amount of rainfall in millimeters on a given day, categorize the rainfall as:
- **LIGHT** if less than 3 mm
- **MODERATE** if between 3 and 6 mm (inclusive of 3 but not 7)
- **HEAVY** if 7 mm or more

---

## ✅ My Code

```c
#include <stdio.h>

int main()
{
    int t,x;
    scanf("%d",&t);
    while(t--)
    {
        scanf("%d",&x);
        if(x<3)
        {
            printf("LIGHT\n");
        }
        else if(x>=3 && x<7)
        {
            printf("MODERATE\n");
        }
        else 
        {
            printf("HEAVY\n");
        }
    }
    return 0;
}
```
## 💡 Explanation
Read the number of test cases t.

For each test case, read the integer x representing the amount of rainfall.

Use conditional statements to classify the rainfall:

If x < 3, print LIGHT

If 3 ≤ x < 7, print MODERATE

If x ≥ 7, print HEAVY

This problem checks basic if-else condition handling in C and input reading logic.

🧠 Time Complexity: O(t)
📦 Space Complexity: O(1)

---



## ✅ 2. SCALENE 


# 🧩 Problem: Scalene Triangle Check (`SCALENE`)
🔗 [Link to Problem](https://www.codechef.com/START69D/problems/SCALENE)

- 📅 **Contest:** Starters 69 Division 2  
- 📆 **Date:** 1 June 2022  
- 🚩 **Difficulty:** Beginner

---

## 📝 Problem Statement (Short Summary)

Given three angles of a triangle, determine if it is **Scalene**.  
A triangle is scalene if **no two angles are equal**.

---

## ✅ My Code

```c
#include <stdio.h>

int main(void) {
    int t,A,B,C;
    scanf("%d",&t);
    while(t--)
    {
        scanf("%d %d %d",&A,&B,&C);
        if(A!=B && B!=C && A!=C)
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
Read the number of test cases t.

For each test case, read three integers A, B, and C representing the angles of the triangle.

A triangle is scalene only if all three angles are distinct.

The condition A != B && B != C && A != C ensures no two angles are equal.

If the condition holds, print YES; otherwise, print NO.

🧠 Time Complexity: O(t)
📦 Space Complexity: O(1)
