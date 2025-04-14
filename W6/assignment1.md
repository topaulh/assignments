## Code

``Java
import java.util.Deque;
import java.util.ArrayDeque;
import java.util.Scanner;

public class PalindromeChecker {

    /**
     * Checks whether the provided text is a palindrome.
     * It ignores any non-alphanumeric characters (such as punctuation and spaces).
     * Assumes that the input string is in lowercase.
     *
     * @param text The input string to be checked.
     * @return true if the string is a palindrome; false otherwise.
     */
    public static boolean isPalindrome(String text) {
        // Create a Deque to store characters of the string
        Deque<Character> deque = new ArrayDeque<>();
        
        // Process each character: add only alphanumeric characters (ignore punctuation and spaces)
        for (int i = 0; i < text.length(); i++) {
            char ch = text.charAt(i);
            if (Character.isLetterOrDigit(ch)) {
                deque.add(ch);
            }
        }
        
        // Special case: A one-character (or empty) string is a palindrome.
        if (deque.size() <= 1) {
            return true;
        }
        
        // Compare characters from the front and back until the deque is empty or a mismatch is found
        while (deque.size() > 1) {
            if (deque.removeFirst() != deque.removeLast()) {
                return false;
            }
        }
        
        return true;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter a string: ");
        String input = scanner.nextLine();
        
        // Check for palindrome and display the corresponding output.
        if (isPalindrome(input)) {
            System.out.println("Yes, " + input + " is a palindrome.");
        } else {
            System.out.println("No, \"" + input + "\" is not a palindrome.");
        }
        
        scanner.close();
    }
}
``

![flowchart drawio](https://github.com/user-attachments/assets/344264ef-5212-4f33-b76a-c4e9f08b85da)

A big challenge was following the output format. This included deciding when to put quotation marks on inputs that were not a palindrome,
and making sure the output exactly matches the format shown in the lab instructions.
