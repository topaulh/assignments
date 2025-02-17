## Code

```java
public class TaxTableTools {
   private int[] search =   {   0,  20000, 50000, 100000, Integer.MAX_VALUE };
   private double[] value = { 0.0,   0.10,  0.20,   0.30,              0.40 };
   private int nEntries;

   public TaxTableTools() {
      nEntries = search.length;  // Set the length of the search table
   } 

   public void setTables(int[] newSearch, double[] newValue) {
       if (newSearch.length != newValue.length) {
           throw new IllegalArgumentException("Search and value arrays must be of the same length.");
       }
       this.search = newSearch;
       this.value = newValue;
       this.nEntries = newSearch.length;
   }
   public double getValue(int searchArgument) {
      double result = 0.0;
      boolean keepLooking = true;
      int i = 0;

      while ((i < nEntries) && keepLooking) {
         if (searchArgument <= search[i]) {
            result = value[i];
            keepLooking = false;
         } else {
            ++i;
         }
      } 

      return result;
   } 
}
```

## Code 2

```java
import java.util.Scanner;

public class IncomeTaxMain {    

   // Method to prompt for and input an integer
   public static int getInteger(Scanner input, String prompt) {
      int inputValue;
      
      System.out.println(prompt + ": ");
      inputValue = input.nextInt();
      
      return inputValue;
   }

   public static void main(String [] args) { 
      final String PROMPT_SALARY = "\nEnter annual salary (-1 to exit)";
      Scanner scnr = new Scanner(System.in);
      int annualSalary;
      double taxRate;
      int taxToPay;

      int []    salary   = {   0,  20000, 50000, 100000, Integer.MAX_VALUE };
      double [] taxTable = { 0.0,   0.10,  0.20,   0.30,              0.40 };

      // Access the related class
      TaxTableTools table = new TaxTableTools();

      // Call the setter method in TaxTableTools to supply new tables
      table.setTables(salary, taxTable);

      // Get the first annual salary to process
      annualSalary = getInteger(scnr, PROMPT_SALARY);

      while (annualSalary >= 0) {
         taxRate = table.getValue(annualSalary);
         taxToPay = (int)(annualSalary * taxRate);     // Truncate tax to an integer amount
         System.out.println("Annual Salary: " + annualSalary + 
                            "\tTax rate: " + taxRate +
                            "\tTax to pay: " + taxToPay);

         // Get the next annual salary
         annualSalary = getInteger(scnr, PROMPT_SALARY);
      } 
      
      scnr.close();
```

The biggest challenge was designing a class structure that allowed for both a built in tax table and the ability to update it using a setter method. 
I had to plan how to use arrays for the salary and tax rates to ensure they stayed together. During implementation, testing the setter method was tricky, 
especially when dealing with mismatched arrays. Integrating these changes with the main program was a bit challenging too.

![Flowchart](https://github.com/user-attachments/assets/4b5cd943-d47c-4451-b42a-a15f97136255)
