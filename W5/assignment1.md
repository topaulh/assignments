## Code

``Java
import java.util.Scanner;

public class StepCounter {
    // Shows how to convert steps into miles
    public static double stepsToMiles(int steps) throws Exception {
        if (steps < 0) {
            throw new Exception("Exception: Negative steps entered");
        }
        return steps / 2000.0; // 2000 steps = 1 mile
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter a number of steps: ");
        
        try {
            int steps = sc.nextInt();
            double miles = stepsToMiles(steps);
            System.out.printf("%.2f\n", miles);
        } catch (Exception e) {
            System.out.println(e.getMessage());
        } finally {
            sc.close();
        }
    }
}
``

The challenge was understanding how to handle exceptions properly and deciding where to place the throw and try-catch blocks.


![flowchart3030](https://github.com/user-attachments/assets/ab717597-6eb3-4d8a-b8ed-810f921f902e)


