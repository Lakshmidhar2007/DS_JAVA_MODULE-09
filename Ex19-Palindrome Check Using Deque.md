# Ex19 Palindrome Check Using Deque

## DATE: 20/09/2026

## AIM:

To design a program that checks whether a given message is a palindrome by removing all non-alphanumeric characters, converting all characters to lowercase, and using a deque data structure for comparison.

## Algorithm

1. Read the input message and remove all non-alphanumeric characters.
2. Convert the message to lowercase.
3. Insert each character into a deque.
4. Remove and compare characters from the front and rear of the deque.
5. If all pairs match, print that the message is a palindrome; otherwise, print that it is not a palindrome.

## Program:

```java
/*
Program to check whether a given message is a palindrome by removing all non-alphanumeric characters.
Developed by: LAKSHMIDHAR N
RegisterNumber:  212224230138
*/

import java.util.*;

public class Main {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String input = sc.nextLine();

        Deque<Character> deque = new ArrayDeque<>();

        for (char ch : input.toCharArray()) {
            if (Character.isLetterOrDigit(ch)) {
                deque.addLast(Character.toLowerCase(ch));
            }
        }

        boolean palindrome = true;

        while (deque.size() > 1) {
            if (!deque.removeFirst().equals(deque.removeLast())) {
                palindrome = false;
                break;
            }
        }

        if (palindrome)
            System.out.println("Palindrome");
        else
            System.out.println("Not Palindrome");
    }
}
```

## Output:

<img width="401" height="112" alt="image" src="https://github.com/user-attachments/assets/02f73c62-065e-4a0d-946e-a03d00268a9a" />


## Result:

The program successfully removes all non-alphanumeric characters, converts the text to lowercase, and uses a deque to efficiently compare characters from both ends. Hence, it determines whether the string is a palindrome.
