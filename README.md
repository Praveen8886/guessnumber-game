import java.util.Random;
import java.util.Scanner;

    public class NumberGuessingGame {
        public static void main(String[] args) {
            Scanner scanner = new Scanner(System.in);
            Random r = new Random();

            int minimun = 1;
            int maximum = 1000;
            int secretNumber = r.nextInt(maximum - minimun + 1) + minimun;

            int attempts = 0;
            boolean guessedCorrectly = false;

            System.out.println("Welcome to the Number Guessing Game!");
            System.out.println("I've picked a number between " + minimun + " and " + maximum + ". Try to guess it.");
            System.out.println("testing");
            int count =0;
            while (!guessedCorrectly) {

                if(count >=3){
                    System.out.println("OOPS BETER LUCK NEXT TIME!");
                    break;
                }

                System.out.print("Enter your guess: ");
                int userGuess = scanner.nextInt();
                attempts++;

                if (userGuess == secretNumber) {
                    System.out.println("Congratulations! You guessed it right in " + attempts + " attempts.");
                    guessedCorrectly = true;
                } else if (userGuess < secretNumber) {
                    System.out.println("Try a higher number.");
                } else {
                    System.out.println("Try a lower number.");
                }
                count++;
            }

            scanner.close();
        }
}
