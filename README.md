# Login-Page-

import java.util.ArrayList;
import java.util.Scanner;

public class UserVerification {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        ArrayList<String> usernames = new ArrayList<>();
        ArrayList<String> passwords = new ArrayList<>();

        // User Registration
        System.out.println("===== USER REGISTRATION =====");

        System.out.print("Enter username: ");
        String username = sc.nextLine();

        System.out.print("Enter password: ");
        String password = sc.nextLine();

        if (usernames.contains(username)) {
            System.out.println("User already registered!");
        } else {
            usernames.add(username);
            passwords.add(password);
            System.out.println("Registration successful!");
        }

        // User Verification
        System.out.println("\n===== USER LOGIN =====");

        System.out.print("Enter username: ");
        String loginUser = sc.nextLine();

        System.out.print("Enter password: ");
        String loginPass = sc.nextLine();

        int index = usernames.indexOf(loginUser);

        if (index != -1 &&
            passwords.get(index).equals(loginPass)) {

            System.out.println("Login successful!");
            System.out.println("Welcome " + loginUser);

        } else if (index == -1) {

            System.out.println("User is not registered!");

        } else {

            System.out.println("Incorrect password!");
        }

        sc.close();
    }
}
