# Java-Security-Password-Checker

This Java program, named PasswordChecker, prompts the user to input a password and checks its security based on several criteria. It utilizes the Scanner class to receive the password and then checks its security using the isSecurePassword method. This method ensures that the password is at least 8 characters long and includes at least one uppercase letter, one lowercase letter, one digit, and one special character. If the password meets all these conditions, the program confirms that the password is secure; otherwise, it informs the user that the password is not secure. The program is designed to help users create stronger and more secure passwords by enforcing a comprehensive set of security rules.


    import java.util.Scanner;

    public class PasswordChecker {
    public static void main(String[] args){
    
        Scanner input = new Scanner(System.in);
        System.out.print("Enter a password: ");
        String password = input.nextLine();

        if (isSecurePassword(password)) {
            System.out.println("The password is secure.");
        } else {
            System.out.println("The password is not secure.");
        }
    }

    public static boolean isSecurePassword(String password) {
        // Check if password length is at least 8 characters
        if (password.length() < 8) {
            return false;
        }

        // Check if password contains at least one uppercase letter
        if (!password.matches(".*[A-Z].*")) {
            return false;
        }

        // Check if password contains at least one lowercase letter
        if (!password.matches(".*[a-z].*")) {
            return false;
        }

        // Check if password contains at least one digit
        if (!password.matches(".*\\d.*")) {
            return false;
        }

        // Check if password contains at least one special character
        if (!password.matches(".*[!@#$%^&*()_+\\-=\\[\\]{};':\"\\\\|,.<>\\/?].*")) {
            return false;
        }

        // If all checks pass, return true
        return true;
    }
}
