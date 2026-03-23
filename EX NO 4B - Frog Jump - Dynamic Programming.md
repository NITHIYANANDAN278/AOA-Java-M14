
# EX 4B Frog Jump - Dynamic Programming.
## DATE: 28/02/2026
## AIM:
To write a Java program to for given constraints.
A Frog Jump 1 or 2 steps at a time.
Problem Statement:

A frog is at the bottom of the stairs with n steps. It can jump either 1 or 2 steps at a time. Write a program to find the number of distinct ways the frog can reach the top (n-th step).

Input Format:

A single integer n (1 ≤ n ≤ 45) – number of steps.
 Output Format:

A single integer – number of distinct ways to reach step n.

## Algorithm
1. Read the value of `n` (number of steps).
2. If `n` is 0 or 1, return 1 (only one way).
3. Create an array `dp[]` of size `n + 1`.
4. Initialise `dp[0] = 1` and `dp[1] = 1`.
5. For each step from 2 to n, compute:
   `dp[i] = dp[i − 1] + dp[i − 2]`
6. The final answer is stored in `dp[n]`.
7. Print the result. 

## Program:
```
/*
Program to implement Reverse a String
Developed by: Nithiyanandan N
Register Number: 212222230099

import java.util.Scanner;

public class FrogJump {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
       
        int n = scanner.nextInt();
        scanner.close();

        System.out.println(countWays(n));
    }

   
    public static int countWays(int n) {
       //Type your code here
       if (n==1) return 1;
       if (n==2) return 2;
       int[] array = new int[n+1];
       array[1]=1;
       array[2]=2;
       for(int i =3;i<=n;i++)
       {
           array[i]=array[i-1]+array[i-2];
       }
       
       return array[n];
    }
}

*/
```

## Output:
<img width="441" height="212" alt="image" src="https://github.com/user-attachments/assets/51afed23-0a95-43d0-87b2-861b620f9fc0" />



## Result:
The program successfully implemented and the expected output is verified.
