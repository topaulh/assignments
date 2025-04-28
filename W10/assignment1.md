// Code

``Java
import javax.swing.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class SalaryCalculator extends JFrame implements ActionListener {
    private JTextField wageField;
    private JTextField hoursField;
    private JButton calculateButton;
    private JLabel resultLabel;

    public SalaryCalculator() {
        setTitle("Yearly Salary Calculator");
        setSize(300, 200);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(null);

        JLabel wageLabel = new JLabel("Hourly Wage");
        wageLabel.setBounds(10, 10, 100, 25);
        add(wageLabel);

        wageField = new JTextField();
        wageField.setBounds(120, 10, 150,
``

A challenge I faced was trying to deal with invalid user output, I fixed it using a try/catch block that shows an error message. Another challenge was making the GUI layout look nice.
I learned that its good to test different window sizes.

![Flowchart3939](https://github.com/user-attachments/assets/5a8b3390-fb06-4dc1-9290-136ada35295b)
