# ATM
import java.util.Scanner;

public class ATM {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int correctPin = 1234;
        double balance = 5000;

        System.out.print("Enter PIN: ");
        int pin = sc.nextInt();

        if (pin != correctPin) {
            System.out.println("Incorrect PIN!");
            return;
        }

        System.out.println("Login successful!");

        while (true) {

            System.out.println("\n===== ATM MENU =====");
            System.out.println("1. Check Balance");
            System.out.println("2. Deposit Money");
            System.out.println("3. Withdraw Money");
            System.out.println("4. Exit");

            System.out.print("Enter your choice: ");
            int choice = sc.nextInt();

            if (choice == 1) {

                System.out.println("Balance: ₹" + balance);

            } else if (choice == 2) {

                System.out.print("Enter amount to deposit: ");
                double amount = sc.nextDouble();

                if (amount > 0) {
                    balance += amount;
                    System.out.println("Money deposited successfully!");
                    System.out.println("New Balance: ₹" + balance);
                } else {
                    System.out.println("Invalid amount!");
                }

            } else if (choice == 3) {

                System.out.print("Enter amount to withdraw: ");
                double amount = sc.nextDouble();

                if (amount <= 0) {
                    System.out.println("Invalid amount!");
                } else if (amount > balance) {
                    System.out.println("Insufficient balance!");
                } else {
                    balance -= amount;
                    System.out.println("Please collect your cash.");
                    System.out.println("Remaining Balance: ₹" + balance);
                }

            } else if (choice == 4) {

                System.out.println("Thank you for using the ATM!");
                break;

            } else {

                System.out.println("Invalid choice!");
            }
        }

        sc.close();
    }
}
