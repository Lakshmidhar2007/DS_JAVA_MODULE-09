# Ex16 Check for Balanced Parentheses Using Stack

## DATE: 20/09/2026

## AIM:

To write a Java program that verifies whether the parentheses (brackets) in an input string are balanced — meaning each opening bracket `(`, `{`, `[` has a corresponding and correctly ordered closing bracket `)`, `}`, `]`.

## Algorithm

1. Read the input string containing brackets.
2. Create a stack to store opening brackets.
3. Push every opening bracket onto the stack.
4. For each closing bracket, check whether it matches the top element of the stack.
5. If all brackets match and the stack is empty, print that the parentheses are balanced; otherwise, print that they are not balanced.

## Program:

```java
/*
Program to verify whether the parentheses (brackets) in an input string are balanced
Developed by: LAKSHMIDHAR N
RegisterNumber:  212224230138
*/

import java.util.*;

public class Main {

    static boolean isBalanced(String str) {
        Stack<Character> stack = new Stack<>();

        for (char ch : str.toCharArray()) {

            if (ch == '(' || ch == '{' || ch == '[') {
                stack.push(ch);
            } 
            else if (ch == ')' || ch == '}' || ch == ']') {

                if (stack.isEmpty())
                    return false;

                char top = stack.pop();

                if ((ch == ')' && top != '(') ||
                    (ch == '}' && top != '{') ||
                    (ch == ']' && top != '[')) {
                    return false;
                }
            }
        }

        return stack.isEmpty();
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String str = sc.nextLine();

        if (isBalanced(str))
            System.out.println("Balanced");
        else
            System.out.println("Not Balanced");
    }
}
```

## Output:

<img width="357" height="122" alt="image" src="https://github.com/user-attachments/assets/71ff93d9-448a-4fcc-b0ff-a9763902e526" />


## Result:

Thus, the program correctly checks whether an input string has balanced parentheses using a stack.
