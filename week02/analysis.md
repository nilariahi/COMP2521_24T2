# Analysis of Algorithms

1.  Design an algorithm to determine if a string of length n is a *palindrome* - that is, it reads the same backwards as forwards. For example, "racecar" is a palindrome, while "reviewer" is not.

    1.  Write the algorithm in pseudocode.

        ```pseudocode
        
        ```
        
    2.  Analyse the worst-case time complexity of your algorithm.
    
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
        ```
    
2.  Using only techniques that you have learned so far, design an algorithm to determine if an array contains two elements that sum to a given value.

    1.  Write the algorithm in pseudocode.
    
        ```pseudocode
        
        ```
        
    2.  Analyse the worst-case time complexity of your algorithm.
    
    3.  Implement your algorithm as a function in C. The algorithm should accept an array and a value as input and return true or false.
    
        ```c
        
        ```