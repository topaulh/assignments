## Code

``Java
import javax.swing.*;
import java.awt.event.*;
import java.text.NumberFormat;

public class DistanceConverter extends JFrame implements ActionListener {
    private JFormattedTextField milesField;
    private JButton convertButton;
    private JLabel kmLabel;
    private JLabel mLabel;
    private JLabel ftLabel;

    public DistanceConverter() {
        setTitle("Distance Converter");
        setSize(350, 250);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(null);

        JLabel milesLabel = new JLabel("Distance (miles):");
        milesLabel.setBounds(10, 20, 120, 25);
        add(milesLabel);

        NumberFormat numberFormat = NumberFormat.getNumberInstance();
        milesField = new JFormattedTextField(numberFormat);
        milesField.setBounds(140, 20, 150, 25);
        add(milesField);

        convertButton = new JButton("Convert");
        convertButton.setBounds(100, 60, 120, 30);
        convertButton.addActionListener(this);
        add(convertButton);

        kmLabel = new JLabel("Kilometers: ");
        kmLabel.setBounds(10, 110, 300, 25);
        add(kmLabel);

        mLabel = new JLabel("Meters: ");
        mLabel.setBounds(10, 140, 300, 25);
        add(mLabel);

        ftLabel = new JLabel("Feet: ");
        ftLabel.setBounds(10, 170, 300, 25);
        add(ftLabel);
    }

    @Override
    public void actionPerformed(ActionEvent e) {
        try {
            double miles = Double.parseDouble(milesField.getText());

            double kilometers = miles * 1.60934;
            double meters = miles * 1609.34;
            double feet = miles * 5280;

            kmLabel.setText(String.format("Kilometers: %.2f km", kilometers));
            mLabel.setText(String.format("Meters: %.2f m", meters));
            ftLabel.setText(String.format("Feet: %.2f ft", feet));
        } catch (NumberFormatException ex) {
            JOptionPane.showMessageDialog(this, "Invalid input! Please enter a number", "Error", JOptionPane.ERROR_MESSAGE);
        }
    }

    public static void main(String[] args) {
        DistanceConverter converter = new DistanceConverter();
        converter.setVisible(true);
    }
}
``

![Assignment2342](https://github.com/user-attachments/assets/57884948-849c-4b2d-9880-8943340c94f3)


A challenge that I dealth with was making sure the input was correct by using JFormattedTextField. Another challenge was trying to put all three conversioanl results in a clean
GUI on the display.
