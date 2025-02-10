# Code

'''Java

    # Method to sort the array in descending order
    public static void sortArray(int[] myArr, int arrSize) {
        // Using bubble sort algorithm.
        for (int i = 0; i < arrSize - 1; i++) {
            for (int j = 0; j < arrSize - i - 1; j++) {
            
                if (myArr[j] < myArr[j + 1]) {
                    int temp = myArr[j];
                    myArr[j] = myArr[j + 1];
                    myArr[j + 1] = temp;
                }
            }
        }
    }
    
    public static void main(String[] args) {
        Scanner scnr = new Scanner(System.in);
        int count = scnr.nextInt();  // The first integer is the number of elements.
        
        int[] numbers = new int[20];
  
        for (int i = 0; i < count; i++) {
            numbers[i] = scnr.nextInt();
        }
    
        sortArray(numbers, count);
        
        # Output the sorted array in the format asked for
        for (int i = 0; i < count; i++) {
            System.out.print(numbers[i]);
            if (i < count - 1) {
                System.out.print(",");
            }
        }
        System.out.println();
        
        scnr.close();
    }
}
'''

![Assignment 1 drawio (2)](https://github.com/user-attachments/assets/7c561f4b-5950-442b-8a3b-980b1c552b64)
