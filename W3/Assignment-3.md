# Code

```java
public class MemoryManagement {

    private int[] data;

    public MemoryManagement(int size) {
        data = new int[size];
        for (int i = 0; i < size; i++) {
            data[i] = i;
        }
    }

    public void printData() {
        for (int num : data) {
            System.out.print(num + " ");
        }
        System.out.println();
    }

    public static void main(String[] args) {
        MemoryManagement management = new MemoryManagement(10);

        demo.printData();

        demo = null;

        System.gc();

        System.out.println("End of main.");
    }
}
```

![45 drawio](https://github.com/user-attachments/assets/9fbabcc6-db45-4213-9c43-f5d90a572ba1)

It was hard to map the variables and objects between the stack and the heap. Picturing how the garbage collection worked and putting it into a flowchart
made me rethink the design multiple times.
