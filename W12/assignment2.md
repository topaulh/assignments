## Code

```Java
import java.util.Scanner;

public class MergeSort {
    static int comparisons = 0;
    static int swaps = 0;

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // Read input
        String[] input = sc.nextLine().split(" ");
        int size = Integer.parseInt(input[0]);
        int[] arr = new int[size];
        for (int i = 0; i < size; i++) {
            arr[i] = Integer.parseInt(input[i + 1]);
        }

        // Output unsorted array
        System.out.print("unsorted: ");
        printArray(arr);

        // Perform merge sort
        mergeSort(arr, 0, size - 1);

        // Output sorted array and stats
        System.out.print("sorted:   ");
        printArray(arr);
        System.out.println("comparisons: " + comparisons);
    }

    static void mergeSort(int[] arr, int left, int right) {
        if (left < right) {
            int mid = (left + right) / 2;

            mergeSort(arr, left, mid);
            mergeSort(arr, mid + 1, right);

            merge(arr, left, mid, right);
        }
    }

    static void merge(int[] arr, int left, int mid, int right) {
        int n1 = mid - left + 1;
        int n2 = right - mid;

        int[] L = new int[n1];
        int[] R = new int[n2];

        for (int i = 0; i < n1; i++) L[i] = arr[left + i];
        for (int j = 0; j < n2; j++) R[j] = arr[mid + 1 + j];

        int i = 0, j = 0, k = left;

        while (i < n1 && j < n2) {
            comparisons++;
            if (L[i] <= R[j]) {
                arr[k++] = L[i++];
            } else {
                arr[k++] = R[j++];
            }
            swaps++; // Every placement is treated as a 'swap'
        }

        while (i < n1) {
            arr[k++] = L[i++];
            swaps++;
        }

        while (j < n2) {
            arr[k++] = R[j++];
            swaps++;
        }
    }

    static void printArray(int[] arr) {
        for (int num : arr) {
            System.out.print(num + " ");
        }
        System.out.println();
    }
}
```
![flowchart303030](https://github.com/user-attachments/assets/b9c77362-876e-4974-97a6-c88cfd328ea7)

A big challenge for me was trying to understand how merge sorting works and trying to see where to count the comparisons and swaps. At first, I accidentally counted comparisons
during the array copying and that made the results bigger.



