# 🧩 Problem: Summing It Up (`SUMM`)
🔗 [Link to Problem](https://www.codechef.com/problems/SUMM)

- 📅 **Contest:** Practice Section  
- 📆 **Date:** July 2022  
- 🚩 **Difficulty:** Beginner  
- 👨‍💻 Language: C

---

## 📝 Problem Statement (Short Summary)

Given three integers `a`, `b`, and `c`, determine whether `a + b = c`.  
If yes, print `YES`. Otherwise, print `NO`.

---

## ✅ My Code

```c
#include <stdio.h>

int main(void) {
    int t,a,b,c;
    scanf("%d",&t);
    while(t--)
    {
        scanf("%d %d %d",&a,&b,&c);
        if(a+b==c)
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

For each test case:

Input three integers: a, b, and c.

If a + b == c, then the condition holds and we print YES.

Otherwise, print NO.

This is a basic check for addition correctness.

🧠 Time Complexity: O(t)
📦 Space Complexity: O(1)



---

## ✅ 2. Problem: **INDIVISIBLE**


# 🧩 Problem: Indivisible Triplet (`INDIVISIBLE`)
🔗 [Link to Problem](https://www.codechef.com/problems/INDIVISIBLE)

- 📅 **Contest:** Practice Section  
- 📆 **Date:** July 2022  
- 🚩 Difficulty: Beginner  
- 👨‍💻 Language: C

---

## 📝 Problem Statement (Short Summary)

Given three integers `a`, `b`, and `c`, find the smallest integer `i` such that `1 ≤ i ≤ 100` and none of the three numbers is divisible by `i`.

---

## ✅ My Code

```c
#include <stdio.h>

int main(void) {
    int t,i,a,b,c,k=100;
    scanf("%d",&t);
    while(t--)
    {
        scanf("%d %d %d",&a,&b,&c);
        for(i=1;i<=k;i++)
        {
            if(a%i!=0 && b%i!=0 && c%i!=0)
            {
                printf("%d\n",i);
                break;
            }
        }
    }
    return 0;
}
```
## 💡 Explanation
Read the number of test cases t.

For each test case:

Input three integers: a, b, and c.

Loop through values of i from 1 to 100.

For each i, check whether all three numbers are not divisible by i:

i.e., a % i != 0, b % i != 0, and c % i != 0.

Print the first such i that satisfies this condition.

This is a brute-force approach and works efficiently due to the small limit of i ≤ 100.

🧠 Time Complexity: O(t * k) where k = 100
📦 Space Complexity: O(1)
