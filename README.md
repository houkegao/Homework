import java.util.Scanner;

public class HighScoreWins {
    public static void main(String[] args) {
        // Create a Scanner object to read user input
        Scanner scanner = new Scanner(System.in);

        // Prompt the user for a game score
        System.out.print("Please enter a game score: ");
        String input = scanner.nextLine();

        // Split the input string on the pipe character (|)
        String[] parts = input.split("\\|");

        // Split the first part (team names) on the colon character (:)
        String[] teams = parts[0].split(":");
        String homeTeam = teams[0];
        String visitorTeam = teams[1];

        // Split the second part (scores) on the colon character (:)
        String[] scores = parts[1].split(":");
        int homeScore = Integer.parseInt(scores[0]);
        int visitorScore = Integer.parseInt(scores[1]);

        // Determine the winner based on the scores
        String winner;
        if (homeScore > visitorScore) {
            winner = homeTeam;
        } else {
            winner = visitorTeam;
        }

        // Display the name of the winning team
        System.out.println("Winner: " + winner);

        // Close the scanner to prevent resource leak
        scanner.close();
    }
}
