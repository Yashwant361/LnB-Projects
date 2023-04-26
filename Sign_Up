package Learn_and_Build;

import java.util.Scanner;

public class Sign_Up {
    public static void main(String[] args) {
        String[] usernames = new String[10]; // array to store usernames

        String[] passwords = new String[10]; // array to store passwords
        int count = 0; // variable to keep track of the number of users signed up

        Scanner input = new Scanner(System.in);

        // loop to allow multiple sign ups
        while (true) {
            System.out.println("Enter a username:");
            String username = input.nextLine();

            // check if the username already exists
            boolean usernameExists = false;
            for (int i = 0; i < count; i++) {
                if (usernames[i].equals(username)) {
                    System.out.println("That username already exists. Please choose another.");
                    usernameExists = true;
                    break;
                }
            }
            if (usernameExists) {
                continue; // start the loop over again to prompt for a new username
            }

            System.out.println("Enter a password:");
            String password = input.nextLine();

            // store the new user's credentials
            usernames[count] = username;
            passwords[count] = password;
            count++;

            System.out.println("Sign up successful!");

            System.out.println("Do you want to sign up another user? (y/n)");
            String choice = input.nextLine();
            if (choice.equalsIgnoreCase("n")) {
                break; // exit the loop if the user chooses not to sign up another user
            }
        }

        // display all signed up users
        System.out.println("All signed up users:");
        for (int i = 0; i < count; i++) {
            System.out.println(usernames[i] + " - " + passwords[i]);
        }
    }
}
