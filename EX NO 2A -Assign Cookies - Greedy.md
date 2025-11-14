# EX 2A - ASSIGN COOKIES

**Date:** 28/08/2025  
**Developed by:** Joel John Jobinse  
**Register Number:** 212223240062  

---

## AIM:
To write a Java program to find the maximum number of children who can be content with the available cookies using a greedy approach.

---

## THEORY:
The **Assign Cookies** problem is a classic greedy algorithm problem.  
Each child has a “greed factor” and each cookie has a “size.”  
A child is satisfied if the cookie size is **greater than or equal** to their greed factor.  
By sorting both arrays and giving each child the smallest possible cookie that satisfies them, we maximize the total number of satisfied children.

---

## ALGORITHM:
1. Start the program.  
2. Read the number of children `n` and their greed factors `g[]`.  
3. Read the number of cookies `m` and their sizes `s[]`.  
4. Sort both arrays in ascending order.  
5. Initialize two pointers `i` (for children) and `j` (for cookies).  
6. While both arrays are not exhausted:  
   - If `s[j] >= g[i]`, assign the cookie and move to the next child (`i++`).  
   - Move to the next cookie (`j++`).  
7. Print the number of satisfied children (`i`).  
8. Stop the program.

---

## PROGRAM:
```java
import java.util.*;

public class AssignCookies {
    
    public static int findContentChildren(int[] g, int[] s) {
        Arrays.sort(g);
        Arrays.sort(s);
        int i = 0, j = 0;
        while (i < g.length && j < s.length) {
            if (s[j] >= g[i]) i++;
            j++;
        }
        return i;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] g = new int[n];
        for (int i = 0; i < n; i++) g[i] = sc.nextInt();
        int m = sc.nextInt();
        int[] s = new int[m];
        for (int i = 0; i < m; i++) s[i] = sc.nextInt();
        System.out.println(findContentChildren(g, s));
    }
}
```

## Output:
<img width="324" height="305" alt="image" src="https://github.com/user-attachments/assets/70337a34-313d-434b-b4e1-b6e81561bd50" />



## Result:
The program successfully print all the numbers from 1 to N. 
