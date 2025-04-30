## Code

``Java
import java.util.Scanner;

public class InsertionSort {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        String[] input = sc.nextLine().split(" ");
        int size = Integer.parseInt(input[0]);
        int[] arr = new int[size];
        for (int i = 0; i < size; i++) {
            arr[i] = Integer.parseInt(input[i + 1]);
        }

        printArray(arr);

        int comparisons = 0;
        int swaps = 0;

        for (int i = 1; i < size; i++) {
            int key = arr[i];
            int j = i - 1;

            boolean didSwap = false;
            while (j >= 0) {
                comparisons++;
                if (arr[j] > key) {
                    arr[j + 1] = arr[j];
                    swaps++;
                    j--;
                    didSwap = true;
                } else {
                    break;
                }
            }
            arr[j + 1] = key;

            printArray(arr); // print after each pass
        }

        System.out.println("comparisons: " + comparisons);
        System.out.println("swaps: " + swaps);
    }

    private static void printArray(int[] arr) {
        for (int value : arr) {
            System.out.print(value + " ");
        }
        System.out.println();
    }
}
``

![flowchart2131](https://github.com/user-attachments/assets/3e5cfc0a-dabe-46c0-a267-cc4484b24165)

One of the biggest challenges I dealt with was tracking the number of comparisons and swaps I was doing. At first, I was struggling to see the exact parts of the insertion
sort loop where I should count the comparisons. And especially was there was no swap that occured.

