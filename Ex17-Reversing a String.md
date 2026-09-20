# Ex17 Reversing a String Using Stack Data Structure

## DATE: 20/09/2026

## AIM:

To write a Java program that reverses an input string using a stack, without using built-in reverse functions.

## Algorithm

1. Read the input string from the user.
2. Create an empty stack of characters.
3. Push each character of the string into the stack.
4. Pop characters from the stack one by one to form the reversed string.
5. Display the reversed string.

## Program:

```java
/*
Program to reverse an input string using a stack
Developed by: LAKSHMIDHAR N
RegisterNumber:  212224230138
*/

import java.util.*;

public class Main {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String str = sc.nextLine();
        Stack<Character> stack = new Stack<>();

        for (char ch : str.toCharArray()) {
            stack.push(ch);
        }

        while (!stack.isEmpty()) {
            System.out.print(stack.pop());
        }
    }
}
```

## Output:

<img width="363" height="85" alt="image" src="https://github.com/user-attachments/assets/59df318a-1e27-4c81-98b5-b05fcb06e3ba" />


## Result:

Thus, the program successfully reverses the given string using a stack without relying on built-in reverse functions.
