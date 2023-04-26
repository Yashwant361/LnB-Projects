package Learn_and_Build;

//BufferedReader is a class that allows efficient reading of text from a character-input stream.
import java.io.BufferedReader;
// BufferedReader is a class that allows efficient reading of text from a character-output stream..
import java.io.BufferedWriter;
// FileReader is a class that reads character files.
import java.io.FileReader;
//FileWriter is a class that writes character files.
import java.io.FileWriter;
// IOException is a class that is used to handle errors
import java.io.IOException;
//Scanner is a class that is used to read input from the console or other input sources.
import java.util.Scanner;

public class RegistrationAndLogin {

    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);
        int choice;

        do {
            System.out.println("Welcome to the program!");
            System.out.println("1. Register");
            System.out.println("2. Login");
            System.out.println("3. Exit");
            System.out.print("Enter your choice: ");
            choice = scanner.nextInt();
            scanner.nextLine(); // consume the newline character

            switch (choice) {
                case 1:
                    registerUser(scanner);
                    break;
                case 2:
                    loginUser(scanner);
                    break;
                case 3:
                    System.out.println("Exiting program...");
                    break;
                default:
                    System.out.println("Invalid choice. Try again.");
                    break;
            }
        } while (choice != 3);

        scanner.close();
    }

    private static void registerUser(Scanner scanner) {
        System.out.println("Enter your name:");
        String name = scanner.nextLine();
        System.out.println("Enter your email address:");
        String email = scanner.nextLine();
        System.out.println("Enter your password:");
        String password = scanner.nextLine();

        //The write() method of the BufferedWriter object is called to write the user's information to the file(txt).

        try (BufferedWriter writer = new BufferedWriter(new FileWriter("users.txt", true))) {
            writer.write(name + "," + email + "," + password + "\n");
            System.out.println("Registration successful!");
        } catch (IOException e) {
            System.out.println("Error writing to file: " + e.getMessage());
        }
    }

    private static void loginUser(Scanner scanner) {
        System.out.println("Enter your email address:");
        String email = scanner.nextLine();
        System.out.println("Enter your password:");
        String password = scanner.nextLine();

        try (BufferedReader reader = new BufferedReader(new FileReader("users.txt"))) {
            String line;
            boolean found = false;
            while ((line = reader.readLine()) != null) {
                String[] parts = line.split(",");
                if (parts.length == 3 && parts[1].equals(email) && parts[2].equals(password)) {
                    found = true;
                    break;
                }
            }
            if (found) {
                System.out.println("Login successful!");
            } else {
                System.out.println("Invalid email or password. Try again.");
            }
        } catch (IOException e) {
            System.out.println("Error reading from file: " + e.getMessage());
        }
    }
}
