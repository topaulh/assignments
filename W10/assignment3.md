##Code

``Java
import javax.swing.*;
import java.awt.event.*;

public class DistanceConverterSpinner extends JFrame implements ActionListener {
    private JSpinner milesSpinner;
    private JButton convertButton;
    private JLabel resultLabel;

    public DistanceConverterSpinner() {
        setTitle("Miles to Kilometers Converter");
        setSize(300, 200);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(null);

        JLabel milesLabel = new JLabel("Distance (miles):");
        milesLabel.setBounds(10, 20, 120, 25);
        add(milesLabel);

        SpinnerNumberModel model = new SpinnerNumberModel(0.0, 0.0, 10000.0, 0.1);
        milesSpinner = new JSpinner(model);
        milesSpinner.setBounds(140, 20, 100, 25);
        add(milesSpinner);

        convertButton = new JButton("Convert");
        convertButton.setBounds(80, 60, 120, 30);
        convertButton.addActionListener(this);
        add(convertButton);

        resultLabel = new JLabel("Kilometers: ");
        resultLabel.setBounds(10, 110, 250, 25);
        add(resultLabel);
    }

    @Override
    public void actionPerformed(ActionEvent e) {
        double miles = (Double) milesSpinner.getValue();
        double kilometers = miles * 1.60934;

        resultLabel.setText(String.format("Kilometers: %.2f km", kilometers));
    }

    public static void main(String[] args) {
        DistanceConverterSpinner converter = new DistanceConverterSpinner();
        converter.setVisible(true);
    }
}
``

A big challenge I faced was trying to make the JSpinner accept decimals, not just integers. I fixed it by 
using a JSpinnerNumberModel with step size 0.1.

![Flowchart39390](https://github.com/user-attachments/assets/ea87b18d-831c-47f7-a599-f19a16502663)
