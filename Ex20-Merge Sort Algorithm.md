# Ex20 Sorting an Array using Merge Sort Algorithm

## DATE: 20/09/2026

## AIM:

To design a program that sorts a given array of integers in ascending order without using built-in sorting functions, achieving O(n log n) time complexity and minimal space usage.

## Algorithm

1. Read the number of elements and store the elements in an array.
2. Divide the array into two halves recursively until each subarray contains one element.
3. Compare the elements of the divided subarrays and merge them in sorted order.
4. Continue merging the subarrays until the complete array is sorted.
5. Display the sorted array in ascending order.

## Program:

```java id="3s5h0m"
/*
Program to sort a given array of integers in ascending order without using built-in sorting functions
Developed by: LAKSHMIDHAR N
RegisterNumber:  212224230138
*/

import java.util.*;

public class Main {

    static void mergeSort(int[] arr, int left, int right) {
        if (left >= right)
            return;

        int mid = (left + right) / 2;

        mergeSort(arr, left, mid);
        mergeSort(arr, mid + 1, right);

        merge(arr, left, mid, right);
    }

    static void merge(int[] arr, int left, int mid, int right) {
        int[] temp = new int[right - left + 1];

        int i = left;
        int j = mid + 1;
        int k = 0;

        while (i <= mid && j <= right) {
            if (arr[i] <= arr[j])
                temp[k++] = arr[i++];
            else
                temp[k++] = arr[j++];
        }

        while (i <= mid)
            temp[k++] = arr[i++];

        while (j <= right)
            temp[k++] = arr[j++];

        for (i = left, k = 0; i <= right; i++, k++)
            arr[i] = temp[k];
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        int[] arr = new int[n];

        for (int i = 0; i < n; i++)
            arr[i] = sc.nextInt();

        mergeSort(arr, 0, n - 1);

        for (int num : arr)
            System.out.print(num + " ");
    }
}
```

## Output:

<img width="395" height="127" alt="image" src="https://github.com/user-attachments/assets/04b044b3-485a-4ee8-b60c-56f7bc61e481" />


## Result:

The program has been successfully implemented and executed.
It sorts the given array of integers in ascending order using the Merge Sort algorithm with a time complexity of O(n log n) and minimal extra space.
