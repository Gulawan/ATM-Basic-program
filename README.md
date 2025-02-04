# ATM-Basic-program

import java.util.Scanner;

class ATM {
    float Balance = 0.0f;
    int PIN = 1234;
    int enteredPin;
    Scanner sc = new Scanner(System.in);
    
    public void checkPIN() {
        System.out.println("Enter your pin: ");
        
        enteredPin = sc.nextInt();
        if(enteredPin == PIN) {
            menu();
        } else {
            System.out.println("Please, enter a valid pin!!!");
        }
    }
    
    public void menu() {
        System.out.println("<---ATM Menu--->");
        System.out.println("Enter your choice!");
        System.out.println("1. Check A/C Balance");
        System.out.println("2. Withdraw Money");
        System.out.println("3. Deposit Money");
        System.out.println("4. Exit");
        
        
        int opt = sc.nextInt();
        
        if(opt == 1) {
            checkBalance();
        } else if(opt == 2) {
            withdrawMoney();
        } else if(opt == 3) {
            depositMoney();
        } else if(opt == 4) {
           return;
        } else {
            System.out.println("Enter a valid choice!!");
        }
    }
    
    public void checkBalance() {
        System.out.println("Your Balance is: " + Balance);
        menu();
    }
    
    public void withdrawMoney() {
        System.out.println("Enter amount to withdraw: " );
        float amount = sc.nextFloat();
        if(amount > Balance) {
            System.out.println("Insufficient Balance!!!");
        } else{
            Balance = Balance - amount;
            System.out.println("Money withdrawal Successfully!");
            System.out.println("YOur current Balance is: " + Balance);
            
        }
        menu();
    }
    
    public void depositMoney() {
        System.out.println("Enter amount to deposit: ");
        float amount = sc.nextFloat();
        Balance = Balance + amount;
        System.out.println("Your current balance is: " + Balance);
        menu();
        
    }
}





public class Main {
    public static void main (String[] args) {
        
        ATM obj = new ATM();
        obj.checkPIN();
    }
} 
