import java.util.Random;
import java.util.Scanner;

public class GuessingGame 
{
    public static void main (String[]args)
    {
        int answer, guess,attemptsNum = 0;
        final int maxAttempts = 5;
        String str, another = "y";

        Scanner scan = new Scanner(System.in);
        Random generator = new Random();
        answer = generator.nextInt(101)+1;

        System.out.println("Guess a number between 1 and 100");
        System.out.println("Enter your guess (0 to quit):");

        {
            guess = scan.nextInt();
            while (guess != 0)
            {
                if(guess==answer)
                        System.out.println("Right!");
                else if (guess<answer)
                    System.out.println("Your guess was too LOW.");
                else if (guess>answer)
                    System.out.println("Your guess was too HIGH.");
            }

            System.out.println("Want to Play again?(y/n)");
            another = scan.next();

            while (guess != answer && ++attemptsNum < maxAttempts)
                if (attemptsNum == maxAttempts)
                    System.out.println ("The number was " + answer);
    }
}
}
