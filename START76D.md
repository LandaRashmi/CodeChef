# 🚀 CodeChef Weekly Upload – Starters 76 Division 4

🗓️ **Date:** 17 August 2022  
📁 **Contest:** Starters 76 Division 4  
🎯 **Difficulty:** Beginner  
👨‍💻 Language: C

---

## 🧩 Problem 1: Read Pages (`READPAGES`)
🔗 [Link to Problem](https://www.codechef.com/problems/READPAGES)  
🚩 Difficulty: Beginner

---

### 📝 Problem Statement (Short Summary)

Chef has to read `n` pages in total.  
Each day he can read `x` pages, and he has `y` days left.  
Determine if Chef can finish the book in the given time.

---

### ✅ My Code

```c
#include <stdio.h>

int main(void) {
    int t,n,x,y;
    scanf("%d",&t);
    while(t--){
        scanf("%d %d %d",&n,&x,&y);
        if(x*y>=n)
            printf("YES\n");
        else
            printf("NO\n");
    }
    return 0;
}
```
## 💡 Explanation
Input t: number of test cases.

For each test case:

n = total pages to read

x = pages Chef can read in one day

y = days left

Total pages Chef can read = x * y

If x * y ≥ n, Chef can finish reading → print YES.

Otherwise, print NO.

🧠 Time Complexity: O(t)
📦 Space Complexity: O(1)

---

## 🧩 Problem 2: 400m Race (`RACE400M`)
🔗 [Link to Problem](https://www.codechef.com/problems/RACE400M)  
🚩 Difficulty: Beginner

---

### 📝 Problem Statement (Short Summary)

Alice, Bob, and Charlie are running a 400m race.  
You are given the time taken by each of them (`x`, `y`, and `z`).  
Print who wins the race — that is, the person with the **least time**.

---

### ✅ My Code

```c
#include <stdio.h>

int main(void) {
    int t,x,y,z;
    scanf("%d",&t);
    while(t--){
        scanf("%d %d %d",&x,&y,&z);
        if(x<y && x<z)
            printf("ALICE\n");
        else if(y<x && y<z)
            printf("BOB\n");
        else
            printf("CHARLIE\n");
    }
    return 0;
}
```
## 💡 Explanation
Input the number of test cases t.

For each test case:

Read the time taken by Alice (x), Bob (y), and Charlie (z).

Compare the times:

If x is the smallest, print ALICE.

Else if y is the smallest, print BOB.

Otherwise, print CHARLIE.

This uses basic comparison to determine the winner.

🧠 Time Complexity: O(t)
📦 Space Complexity: O(1)
