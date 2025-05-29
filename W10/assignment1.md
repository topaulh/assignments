// Code

```Java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class SalaryCalculator extends JFrame {
    private JTextField wageField, hoursField;
    private JLabel resultLabel;

    public SalaryCalculator() {
        setTitle("Yearly Salary Calculator");
        setSize(350, 200);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new GridLayout(4, 2, 10, 10));

        add(new JLabel("Hourly Wage:"));
        wageField = new JTextField();
        add(wageField);

        add(new JLabel("Hours per Week:"));
        hoursField = new JTextField();
        add(hoursField);

        JButton calcButton = new JButton("Calculate Salary");
        add(calcButton);

        resultLabel = new JLabel("Yearly Salary: ");
        add(resultLabel);

        calcButton.addActionListener(e -> calculateSalary());

        setVisible(true);
    }

    private void calculateSalary() {
        try {
            double wage = Double.parseDouble(wageField.getText());
            double hours = Double.parseDouble(hoursField.getText());
            double yearly = wage * hours * 52;
            resultLabel.setText(String.format("Yearly Salary: $%.2f", yearly));
        } catch (NumberFormatException e) {
            resultLabel.setText("Invalid input.");
        }
    }

    public static void main(String[] args) {
        new SalaryCalculator();
    }
}
```

A challenge I faced was trying to deal with invalid user output, I fixed it using a try/catch block that shows an error message. Another challenge was making the GUI layout look nice.
I learned that its good to test different window sizes.

![Flowchart3939](https://github.com/user-attachments/assets/5a8b3390-fb06-4dc1-9290-136ada35295b)
