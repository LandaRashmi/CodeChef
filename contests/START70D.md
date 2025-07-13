# 🧩 Problem: Kitchen Timings (`KITCHENTIME`)
🔗 [Link to Problem](https://www.codechef.com/problems/KITCHENTIME)

- 📅 **Contest:** Practice Section  
- 📆 **Date:** June 2022  
- 🚩 **Difficulty:** Beginner

---

## 📝 Problem Statement (Short Summary)

Given the start time `x` and end time `y` of Chef’s cooking session, find how long Chef was in the kitchen by computing `y - x`.

---

## ✅ My Code

```c
#include <stdio.h>

int main(void) {
    int t,x,y;
    scanf("%d",&t);
    while(t--)
    {
        scanf("%d %d",&x,&y);
        printf("%d\n",y-x);
    }
    return 0;
}
```
## 💡 Explanation
We read the number of test cases t.

For each test case, two integers x and y represent start and end time.

Subtract x from y to get the total time spent in the kitchen.

Print the result for each test case.

🧠 Time Complexity: O(t)
📦 Space Complexity: O(1)


---

## ✅ 2. KITCHENSPICE 


# 🧩 Problem: Kitchen Spice Level (`KITCHENSPICE`)
🔗 [Link to Problem](https://www.codechef.com/problems/KITCHENSPICE)

- 📅 **Contest:** Practice Section  
- 📆 **Date:** June 2022  
- 🚩 **Difficulty:** Beginner

---

## 📝 Problem Statement (Short Summary)

Given the spiciness level `x` of a dish:
- If `x < 4`, the spice level is **MILD**
- If `4 ≤ x < 7`, it's **MEDIUM**
- If `x ≥ 7`, it's **HOT**

---

## ✅ My Code

```c
#include <stdio.h>

int main(void) {
    int t,x;
    scanf("%d",&t);
    while(t--)
    {
        scanf("%d",&x);
        if(x<4)
        {
            printf("MILD\n");
        }
        else if(x>=4 && x<7)
        {
            printf("MEDIUM\n");
        }
        else
        {
            printf("HOT\n");
        }
    }
    return 0;
}
```
## 💡 Explanation
Read t test cases.

For each test case, input the spice level x.

Use if-else conditions:

x < 4 → MILD

4 ≤ x < 7 → MEDIUM

x ≥ 7 → HOT

Print the spice category for each test case.

🧠 Time Complexity: O(t)
📦 Space Complexity: O(1)


---

## ✅ 3. KITCHENCOST 

# 🧩 Problem: Kitchen Cost (`KITCHENCOST`)
🔗 [Link to Problem](https://www.codechef.com/problems/KITCHENCOST)

- 📅 **Contest:** Practice Section  
- 📆 **Date:** June 2022  
- 🚩 **Difficulty:** Easy

---

## 📝 Problem Statement (Short Summary)

Given:
- An array `a[]` representing the spiciness of ingredients
- An array `b[]` representing the cost of those ingredients
- A minimum spiciness threshold `x`

Find the total cost of all ingredients with spiciness **greater than or equal to** `x`.

---

## ✅ My Code

```c
#include <stdio.h>

int main(void) {
    int a[100],b[100];
    int t,i,n,x,s;
    scanf("%d",&t);
    while(t--)
    {
        scanf("%d %d",&n,&x);
        for(i=0;i<n;i++)
        {
            scanf("%d ",&a[i]);
        }
        for(i=0;i<n;i++)
        {
            scanf("\n%d ",&b[i]);
        }
        s=0;
        for(i=0;i<n;i++)
        {
            if(a[i]>=x)
            {
                s=s+b[i];
            }
        }
        printf("%d\n",s);
    }
    return 0;
}
```
## 💡 Explanation
For each test case:

Read the number of ingredients n and spiciness threshold x

Read two arrays: a[] for spiciness, b[] for cost

Loop through each ingredient:

If a[i] >= x, add b[i] to the total cost

Print the total cost for each test case

🧠 Time Complexity: O(n) per test case
📦 Space Complexity: O(n)
