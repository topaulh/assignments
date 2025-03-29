## Code

``Java
import java.time.LocalDate;
import java.time.format.DateTimeParseException;

public class InventoryControlSystem {
    public static void main(String[] args) {
        // Inventory Control System - Version 1.0
        System.out.println("Inventory Control System - V1");
        InventoryItem item1 = new Painkiller("Aspirin", "Bayer", 0.5);
        InventoryItem item2 = new Bandage("BandAid", "3M", 0.1);
        InventoryItem item3 = new Equipment("Stethoscope", "GE", 1.5);

        item1.display();
        item2.display();
        item3.display();
 
        System.out.println("Updating painkiller using full update");
        item1.update("Aspirin Extra", "Bayer", 0.6);
        item1.display();

        System.out.println("Updating painkiller using overload update");
        item1.update("Super Aspirin");
        item1.display();
        
        
        // Inventory Control System V2

        System.out.println("Inventory Control System V2");
        try {
            InventoryItem invalidItem = new Painkiller("", "Bayer", 0.5);
        } catch (IllegalArgumentException e) {
            System.out.println("Caught exception: " + e.getMessage());
        }
        try {
            InventoryItem invalidItem2 = new Bandage("BandAid", "", 0.1);
        } catch (IllegalArgumentException e) {
            System.out.println("Caught exception: " + e.getMessage());
        }
        try {
            InventoryItem invalidItem3 = new Equipment("Stethoscope", "GE", -1.5);
        } catch (IllegalArgumentException e) {
            System.out.println("Caught exception: " + e.getMessage());
        }

        // Inventory Control System - V3

        System.out.println("Inventory Control System V3");
        try {
            // Create an inventory item new attributes:
            // expiryDate (format YYYY-MM-DD), ageGroup, and waterproof indicator.
            EnhancedInventoryItem enhancedItem = new EnhancedInventoryItem("PainRelief", "Pfizer", 0.3, "2024-12-31", "Adult", 'Y');
            enhancedItem.display();

            System.out.println("Attempting update with invalid expiry date");
            enhancedItem.update("PainRelief", "Pfizer", 0.3, "2020-01-01", "Adult", 'Y');
        } catch (InvalidExpiryDateException e) {
            System.out.println("Caught custom exception: " + e.getMessage());
        }
    }
}


// V1 Classes

class InventoryItem {
    protected String name;
    protected String companyName;
    protected double weight;

    public InventoryItem(String name, String companyName, double weight) {
        if (name == null || name.isEmpty()) {
            throw new IllegalArgumentException("Item name cant be empty");
        }
        if (companyName == null || companyName.isEmpty()) {
            throw new IllegalArgumentException("Company name cant be empty");
        }
        if (weight <= 0) {
            throw new IllegalArgumentException("Weight needs to be positive");
        }
        this.name = name;
        this.companyName = companyName;
        this.weight = weight;
    }

    public void update(String name, String companyName, double weight) {
        if (name == null || name.isEmpty()) {
            throw new IllegalArgumentException("Item name cant be empty");
        }
        if (companyName == null || companyName.isEmpty()) {
            throw new IllegalArgumentException("Company name cant be empty");
        }
        if (weight <= 0) {
            throw new IllegalArgumentException("Weight needs to be positive");
        }
        this.name = name;
        this.companyName = companyName;
        this.weight = weight;
    }

    public void update(String name) {
        if (name == null || name.isEmpty()) {
            throw new IllegalArgumentException("Item name cant be empty");
        }
        this.name = name;
    }
    
    public void display() {
        System.out.println("Item: " + name + ", Company: " + companyName + ", Weight: " + weight + " lbs");
    }
}

class Painkiller extends InventoryItem {
    public Painkiller(String name, String companyName, double weight) {
        super(name, companyName, weight);
    }

    @Override
    public void display() {
        System.out.println("Painkiller - Item: " + name + ", Company: " + companyName + ", Weight: " + weight + " lbs");
    }
}

class Bandage extends InventoryItem {
    public Bandage(String name, String companyName, double weight) {
        super(name, companyName, weight);
    }

    @Override
    public void display() {
        System.out.println("Bandage - Item: " + name + ", Company: " + companyName + ", Weight: " + weight + " lbs");
    }
}

class Equipment extends InventoryItem {
    public Equipment(String name, String companyName, double weight) {
        super(name, companyName, weight);
    }

    @Override
    public void display() {
        System.out.println("Equipment - Item: " + name + ", Company: " + companyName + ", Weight: " + weight + " lbs");
    }
}

// V3 Classes

class InvalidExpiryDateException extends Exception {
    public InvalidExpiryDateException(String message) {
        super(message);
    }
}

// Enhanced inventory item with additional attributes: expiryDate, ageGroup, and waterproof indicator.
class EnhancedInventoryItem extends InventoryItem {
    private LocalDate expiryDate;
    private String ageGroup;
    private char waterproof; // 'Y' or 'N'
    
    public EnhancedInventoryItem(String name, String companyName, double weight, String expiryDate, String ageGroup, char waterproof)
            throws InvalidExpiryDateException {
        super(name, companyName, weight);
        setExpiryDate(expiryDate);
        this.ageGroup = ageGroup;
        this.water
``
