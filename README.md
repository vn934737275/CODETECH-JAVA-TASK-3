import java.util.Scanner;
import java.util.Random;

public class NumberGuessingGame {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        Random random = new Random();
        
        int secretNumber = random.nextInt(100) + 1;
        int maxAttempts = 5;
        int attempts = 0;
        boolean guessedCorrectly = false;
        
        System.out.println("Welcome to the Number Guessing Game!");
        System.out.println("I've picked a number between 1 and 100. Can you guess it?");
        
        while (attempts < maxAttempts && !guessedCorrectly) {
            System.out.print("Enter your guess: ");
            int guess = scanner.nextInt();
            attempts++;
            
            if (guess == secretNumber) {
                guessedCorrectly = true;
                System.out.println("Congratulations! You guessed the number " + secretNumber + " correctly in " + attempts + " attempts!");
            } else if (guess < secretNumber) {
                System.out.println("Too low! Try again.");
            } else {
                System.out.println("Too high! Try again.");
            }
        }
        
        if (!guessedCorrectly) {
            System.out.println("Sorry, you've run out of attempts! The secret number was: " + secretNumber);
        }
        
        scanner.close();
    }
}
