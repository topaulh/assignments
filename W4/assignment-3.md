## Code


``Java
public class Book {
    // Private fields
    private String title;
    private String author;
    private String publisher;
    private String publicationDate;
    
    public void setTitle(String title) {
        this.title = title;
    }
    public void setAuthor(String author) {
        this.author = author;
    }
    public void setPublisher(String publisher) {
        this.publisher = publisher;
    }
    public void setPublicationDate(String publicationDate) {
        this.publicationDate = publicationDate;
    }
    public String getTitle() {
        return title;
    }
    public String getAuthor() {
        return author;
    }
    public String getPublisher() {
        return publisher;
    }
    public String getPublicationDate() {
        return publicationDate;
    }

    // Print book info
    public void printInfo() {
        System.out.println("Book Information: ");
        System.out.println("   Book Title: " + title);
        System.out.println("   Author: " + author);
        System.out.println("   Publisher: " + publisher);
        System.out.println("   Publication Date: " + publicationDate);
    }
}
``

``Java
public class Encyclopedia extends Book {
    // More fields for Encyclopedia
    private String edition;
    private int numberOfPages;

    public void setEdition(String edition) {
        this.edition = edition;
    }
    public void setNumberOfPages(int numberOfPages) {
        this.numberOfPages = numberOfPages;
    }

    public String getEdition() {
        return edition;
    }
    public int getNumberOfPages() {
        return numberOfPages;
    }

    // Override printInfo() method for additional details
    @Override
    public void printInfo() {
        System.out.println("Book Information: ");
        System.out.println("   Book Title: " + getTitle());
        System.out.println("   Author: " + getAuthor());
        System.out.println("   Publisher: " + getPublisher());
        System.out.println("   Publication Date: " + getPublicationDate());
        System.out.println("   Edition: " + edition);
        System.out.println("   Number of Pages: " + numberOfPages);
    }
}
``

``Java
public class Main {
    public static void main(String[] args) {
        // Create Book object and make its values
        Book book1 = new Book();
        book1.setTitle("The Hobbit");
        book1.setAuthor("J. R. R. Tolkien");
        book1.setPublisher("George Allen & Unwin");
        book1.setPublicationDate("21 September 1937");
        
        // Print book info
        book1.printInfo();
        
        System.out.println();
        
        // Create Encyclopedia object and make its values
        Encyclopedia encyclopedia1 = new Encyclopedia();
        encyclopedia1.setTitle("The Illustrated Encyclopedia of the Universe");
        encyclopedia1.setAuthor("Ian Ridpath");
        encyclopedia1.setPublisher("Watson-Guptill");
        encyclopedia1.setPublicationDate("2001");
        encyclopedia1.setEdition("2nd");
        encyclopedia1.setNumberOfPages(384);
        
        // Print encyclopedia info
        encyclopedia1.printInfo();
    }
}
``

![2025flowchart drawio (1)](https://github.com/user-attachments/assets/c1de9c4e-5d85-4114-b054-3642a3573952)

One challenge was making sure that the printInfo() in the Encyclopedia class was overriding the one in the Book class. This required
me to carefully use the @Override annotation and make sure the method signature was the same.



