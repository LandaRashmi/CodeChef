# 💸 CodeChef Weekly Upload – DEC221D

🗓️ **Date:** 9 December 2022  
📁 **Contest:** December Long Challenge 2022 Division 2  
🎯 **Difficulty:** Beginner  
👨‍💻 **Language:** C

---

**🧩 Problem: Investment Planning (`INVESTMENT`)**  
🔗 [Link to Problem](https://www.codechef.com/problems/INVESTMENT)  
🚩 Difficulty: Beginner


### 📝 Problem Statement (Short Summary)

Chef wants to invest in a scheme that doubles his investment.  
He can only invest if the amount he has (`x`) is **at least twice** the required amount (`y`).  
Print **YES** if Chef can invest, otherwise print **NO**.


### ✅ My Code

```c
#include <stdio.h>

int main(void) {
    int t,x,y;
    scanf("%d",&t);
    while(t--)
    {
        scanf("%d %d",&x,&y);
        if(x>=2*y)
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

Read x (Chef’s available amount)

Read y (required amount)

If x ≥ 2 * y, then Chef can invest, so print YES.

Otherwise, print NO.

🧠 Time Complexity: O(t)  
📦 Space Complexity: O(1)
