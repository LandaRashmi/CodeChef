# 🧩 Problem: Apartment Numbers (`MANAPTS`)
🔗 [Link to Problem](https://www.codechef.com/problems/MANAPTS)

- 📅 **Contest:** Starters 74 Division 4  
- 📆 **Date:** 3 August 2022  
- 🚩 **Difficulty:** Beginner  
- 👨‍💻 Language: C

---

## 📝 Problem Statement (Short Summary)

A building has apartments such that each floor contains exactly `x` apartments.  
Given a flat number `y`, find the **floor number** on which it is located.  
Assume flat numbers start from `1` and increase sequentially floor-wise.

---

## ✅ My Code

```c
#include <stdio.h>

int main(void) {
    int t,x,y;
    scanf("%d",&t);
    while(t--){
        scanf("%d %d",&x,&y);
        printf("%d\n",y/x);
    }
    return 0;
}
```
## 💡 Explanation
Read number of test cases t.

For each test case:

Read x → number of apartments per floor

Read y → the flat number

Since each floor has x apartments, floor number = y / x (integer division).

This works because:

Flat numbers from 1 to x are on the 1st floor

From x+1 to 2x on the 2nd floor

So the formula gives correct result with 1-based indexing

Edge cases:

If flat number is exactly divisible by x, this correctly returns its floor.

🧠 Time Complexity: O(t)
📦 Space Complexity: O(1)
