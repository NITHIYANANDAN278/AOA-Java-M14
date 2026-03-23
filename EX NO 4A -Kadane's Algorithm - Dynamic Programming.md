
# EX 4A Kadane's Algorithm - Dynamic Programming. 
## DATE: 27/02/2026
## AIM:
To Write a Java program to solve the below problem using Kadane's Algorithm.
A solar company installs solar panels around a circular grid of n buildings. Each building either generates or consumes net energy, represented by integers (+ve for generated, -ve for consumed).

The company wants to find a contiguous sequence of buildings (possibly wrapping around from the end to the beginning) that maximizes the total net energy.

Write a program to compute the maximum net energy that can be collected from any contiguous block of buildings on the circular grid.

Input Format:
First line: Integer n (number of buildings)

Second line: n space-separated integers: net energy for each building

Output Format:
A single integer: Maximum net energy collectable from a contiguous block (wrapping allowed)

Constraints:
1 <= n <= 10^6
## Algorithm
1. Read the number of buildings `n` and the net energy values.
2. Use **Kadane’s Algorithm** to find the maximum subarray sum (non-circular case).
3. Use **Kadane’s Algorithm (inverted)** to find the minimum subarray sum.
4. Compute the total sum of all energy values.
5. If all values are negative, return the maximum value directly.
6. Otherwise, compute the maximum circular sum as
   `totalSum - minSum`.
7. The answer is the maximum of:

   * Normal maximum subarray sum
   * Circular maximum subarray sum
8. Print the result.
## Program:
```
/*
Program to implement Reverse a String
Developed by: Nithiyanandan N
Register Number:  21222230099
import java.util.*;

public class SolarEnergyMaximizer {

    public static int maxCircularEnergy(int[] energy)     {
        //Type your code
        int total=0;
        int summax = energy[0];
        int currentmax=0;
        int summin = energy[0];
        int currentmin=0;
        for(int e:energy){
            currentmax=Math.max(e,currentmax+e);
            summax=Math.max(summax,currentmax);
            
            currentmin=Math.min(e,currentmin+e);
            summin=Math.min(summin,currentmin);
            
            total+=e;
        }
        if(summax<0) return summax;
        
        return Math.max(summax,total-summin);
    }

    
    

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] energy = new int[n];
        for (int i = 0; i < n; i++) {
            energy[i] = sc.nextInt();
        }
        System.out.println(maxCircularEnergy(energy));
    }
}

*/
```

## Output:
<img width="487" height="245" alt="image" src="https://github.com/user-attachments/assets/82b291d6-f5e6-483b-bb8e-95efe9ac98c1" />



## Result:
The program successfully Implemented and the output is verified. 
