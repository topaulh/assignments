# Code

'''java
import java.util.Scanner;

public class WordFrequencies {

    public static int getWordFrequency(String[] wordsList, int listSize, String currWord) {
        int frequency = 0;
        for (int i = 0; i < listSize; i++) {
            // Compare words ignoring case
            if (wordsList[i].equalsIgnoreCase(currWord)) {
                frequency++;
            }
        }
        return frequency;
    }
    
    public static void main(String[] args) {
        Scanner scnr = new Scanner(System.in);
        // Create an array to hold up to 20 words
        String[] words = new String[20];
        int count = 0;
        
        while (scnr.hasNext() && count < 20) {
            words[count] = scnr.next();
            count++;
        }
        
        for (int i = 0; i < count; i++) {
            int freq = getWordFrequency(words, count, words[i]);
            System.out.println(words[i] + " " + freq);
        }
        
        scnr.close();
    }
}
'''

![Assignment2FlowChart drawio](https://github.com/user-attachments/assets/f96696e8-e41b-4807-9434-d6a6d58cbac3)

If I had to do a frequency analysis of a website, I would get the websites HTML content using a tool or library that can fetch web pages. 
Then I would remove all the HTML tags and convert the text to lowercase so its easier to compare words. Then I would split the text into individual words and
count how many times each word appears using a simple dictionary or similar structure. Last, I would sort the list of words by their count to see which words
appear most often.

I struggled with figuring out the best way to store the input words, also since the number of words could change. I found it 
hard to find the method that would count the frequency of each word in a case non sensitive way.
