
# EX 4E Longest Increasing Subsequence - Dynamic Programming.
## DATE: 04/02/2026
## AIM:
To write a Java program to for given constraints.
Given an integer array nums, return the length of the longest strictly increasing subsequence.
Example 1:
Input: nums = [10,9,2,5,3,7,101,18]
Output: 4
Explanation: The longest increasing subsequence is [2,3,7,101], therefore the length is 4.
## Algorithm
1. Read the array size `n` and the array elements.
2. Create a DP array `dp[]` of size `n`, initialized with 1 (each number is an LIS of length 1).
3. For each index `i` from 1 to n−1:

   * Check previous elements `j` from 0 to i−1.
   * If `nums[i] > nums[j]`, update
     `dp[i] = max(dp[i], dp[j] + 1)`
4. Find the maximum value in the DP array — this is the LIS length.
5. Print the result. 

## Program:
```
/*
Program to implement Reverse a String
Developed by: NITHIYANANDAN N
Register Number: 212222230099
import java.util.*;

public class LongestIncreasingSubsequence {

    public static int lengthOfLIS(int[] nums) {
        int n =nums.length;
        int[] dp = new int[n];
        Arrays.fill(dp,1);
        
        for(int i=1;i<n;i++){
            for(int j=0;j<i;j++){
                if(nums[i]>nums[j]){
                    dp[i]=Math.max(dp[i],dp[j]+1);
                }
            }
        }
        int large=0;
        for(int a:dp){
            large=Math.max(large,a);
        }
        return large;
        // Type Your Code here...!
    }

public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Prompt user input
        int n = scanner.nextInt();
        int[] nums = new int[n];

        for (int i = 0; i < n; i++) {
            nums[i] = scanner.nextInt();
        }

        // Calculate and display the length of LIS
        int result = lengthOfLIS(nums);
        System.out.println("Length of Longest Increasing Subsequence: " + result);

        scanner.close();
    }
}

*/
```

## Output:
<img width="1133" height="238" alt="image" src="https://github.com/user-attachments/assets/ab7267be-69d1-4376-ad53-bef798ecdd93" />



## Result:
The program successfully implemented and the expected output is verified.
