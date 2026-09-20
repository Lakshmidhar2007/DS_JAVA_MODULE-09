# Ex18 Simulation of a Ticket Counter Using Queue (Linked List Implementation)

## DATE: 20/09/2026

## AIM:

To simulate the functioning of a ticket counter that operates on a First-In-First-Out (FIFO) basis using a queue implemented via a linked list in Java.

## Algorithm

1. Create a queue using a linked list with `front` and `rear` pointers.
2. Read the number of customers and insert each customer into the queue.
3. Insert customers at the rear of the queue using the enqueue operation.
4. Remove customers from the front of the queue using the dequeue operation.
5. Display the customers in the order they are served.

## Program:

```java
/*
Program to functioning of a ticket counter that operates on a First-In-First-Out (FIFO)
Developed by: LAKSHMIDHAR N
RegisterNumber:  212224230138
*/

import java.util.*;

public class Main {

    static class Node {
        int data;
        Node next;

        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }

    static class Queue {
        Node front, rear;

        void enqueue(int data) {
            Node newNode = new Node(data);

            if (rear == null) {
                front = rear = newNode;
            } else {
                rear.next = newNode;
                rear = newNode;
            }
        }

        int dequeue() {
            if (front == null)
                return -1;

            int data = front.data;
            front = front.next;

            if (front == null)
                rear = null;

            return data;
        }

        boolean isEmpty() {
            return front == null;
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        Queue queue = new Queue();

        for (int i = 0; i < n; i++) {
            queue.enqueue(sc.nextInt());
        }

        while (!queue.isEmpty()) {
            System.out.print(queue.dequeue() + " ");
        }
    }
}
```

## Output:

<img width="380" height="117" alt="image" src="https://github.com/user-attachments/assets/17e89d2b-192b-40ae-8a50-47b1acce9fcc" />


## Result:

Thus, the program successfully simulates a ticket counter queue where customers are served in FIFO order using a linked list-based queue implementation.
