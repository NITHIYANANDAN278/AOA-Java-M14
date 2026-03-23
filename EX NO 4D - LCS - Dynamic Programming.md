
# EX 4D Longest Common SubSequence - Dynamic Programming.
## DATE: 02/03/2026
## AIM:
To write a Java program to for given constraints.
Given two strings text1 and text2, return the length of their longest common subsequence. If there is no common subsequence, return 0.
A subsequence of a string is a new string generated from the original string with some characters (can be none) deleted without changing the relative order of the remaining characters.

For example, "ace" is a subsequence of "abcde".
A common subsequence of two strings is a subsequence that is common to both strings.

Input: text1 = "abcde", text2 = "ace" 
Output: 3  
Explanation: The longest common subsequence is "ace" and its length is 3.
Constraints:

1 <= text1.length, text2.length <= 1000
text1 and text2 consist of only lowercase English characters.

## Algorithm
1. Read the two input strings `text1` and `text2`.
2. Create a 2D DP matrix `dp[m+1][n+1]` where `m` and `n` are the lengths of the strings.
3. Fill the DP table from bottom-right to top-left:

   * If characters match:
     `dp[i][j] = 1 + dp[i+1][j+1]`
   * Else:
     `dp[i][j] = max(dp[i+1][j], dp[i][j+1])`
4. The value at `dp[0][0]` gives the length of the LCS.
5. Print the result.

## Program:
```
/*
Program to implement Reverse a String
Developed by: Nithiyanandan N
Register Number:  212222230099
*/
import java.util.Scanner;

public class Solution {
  public int longestCommonSubsequence(String text1, String text2) {    
    int n = text1.length();
    int m = text2.length();
    
    int[][] dp = new int[n+1][m+1];
    
    for(int i=1;i<=n;i++){
        for(int j=1;j<=m;j++){
            if(text1.charAt(i-1)==text2.charAt(j-1)){
                dp[i][j]=1+dp[i-1][j-1];
            }
            else{
                dp[i][j]=Math.max(dp[i-1][j],dp[i][j-1]);
            }
        }
    }
    return dp[n][m];
    //ADD YOUR CODE HERE
  }

    // Main method for input and output
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Solution sol = new Solution();

        String text1 = sc.nextLine().replaceAll("\"", "");
        String text2 = sc.nextLine().replaceAll("\"", "");

        int lcsLength = sol.longestCommonSubsequence(text1, text2);
        System.out.println("Length of Longest Common Subsequence: " + lcsLength);

        sc.close();
    }
}

```

## Output:
<img width="980" height="248" alt="image" src="https://github.com/user-attachments/assets/c9382a43-d0c1-43f5-8d84-c3b6b3793e80" />



## Result:
The program successfully implemented and the expected output is verified.
