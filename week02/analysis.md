# Analysis of Algorithms

1.  Design an algorithm to determine if a string of length n is a *palindrome* - that is, it reads the same backwards as forwards. For example, "racecar" is a palindrome, while "reviewer" is not.

    1.  Write the algorithm in pseudocode.

        ```pseudocode
        Input: string s of length n
        Output: "yes" if s is a palindrome, otherwise "no"
        
        palindrome:
        	for i from 0 to n / 2: // O(n)
        		if s[i] != s[n - i - 1] // O(1)
        			print("No") // O(1)
        			return // O(1)
            print("Yes") // O(1)
        ```
    
    2.  Analyse the worst-case time complexity of your algorithm.
    
        $\mathcal{O}(n)$ because in the worst case we loop from the beginning of the string to its halfway point, so the loop has $\frac{n}{2}$ iterations. All other operations are constant time, so we have $\mathcal{O}(\frac{n}{2}) = \mathcal{O}(n)$.
    
    3.  Implement your algorithm in C. Your program should accept a single command line argument, and check whether it is a palindrome. Examples of the program executing are:
    
        ```cmd
        $ ./palindrome racecar
        yes
        $ ./palindrome reviewer
        no
        ```
    
        *Hint:* You may use the standard library function*strlen(3)*, which has prototype `size_t strlen(char *)`, is defined in `<string.h>`, and which computes the length of a string (without counting its terminating `'\0'` character).
    
        ```c
        #include <stdio.h>
        #include <stdlib.h>
        #include <string.h>
        
        int main(int argc, char **argv) {
            // error checking
            if (argc != 2) {
                fprintf("correct usage: %s <arg>\n", argv[0]);
                exit(1);
            }
            
            char *str = argv[1];
            int n = strlen(str);
            
            for (int i = 0; i < n / 2; i++) {
                if (str[i] != str[n - i - 1]) {
                    printf("No\n");
                    return 0;
                }
            }
            
            printf("Yes\n");
            return 0;
        }
        
        ```
    
2.  Using only techniques that you have learned so far, design an algorithm to determine if an array contains two elements that sum to a given value.

    1.  Write the algorithm in pseudocode.
    
        ```pseudocode
        Input: array A of ints of length n, target sum t
        Output: true if 2 distinct elements in A add up to t, else false
        
        twoSum:
        	for i from 0 to n - 1: // O(n)
        		for j from i + 1 to n - 1: // O(n^2)
        			if A[i] + A[j] == t: // O(1)
        				return true // O(1)
            return false // O(1)
        ```
    
    2.  Analyse the worst-case time complexity of your algorithm.
    
        In the worst case, we look at all distinct pairs of elements and don't find 2 that add up to the target sum. In this case our function is $\mathcal{O}(n^2)$ because the outer loop runs $n$ times and within it there's a nested loop that runs $\mathcal{O}(n)$ times by itself, so $\mathcal{O}(n^2)$ times overall. All other operations are primitive, so we have $\mathcal{O}(n^2)$ overall.
    
    3.  Implement your algorithm as a function in C. The algorithm should accept an array and a value as input and return true or false.
    
        ```c
        bool twoSum(int *arr, int n, int targetSum) {
            for (int i = 0; i < n; i++) {
                for (int j = i + 1; j < n; j++) {
                    if (arr[i] + arr[j] == targetSum) {
                        return true;
                    }
                } 
            }
            return false;
        }
        ```
        
    