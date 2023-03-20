###contribuing code

import java.util.*;
public class BankingApplication {
	public static void main(String args[]) {
		BankingApp obj=new BankingApp("example name","example ID");
		obj.show_menu();
	}
}

class BankingApp{
	
	int balance;
	int pre_trans;
	String Customer_name;
	String Customer_id;
	 BankingApp(String C_name,String C_id){
		 
		 Customer_name=C_name;
		 Customer_id=C_id;
	 }
	 
	 void deposit(int amount) {
		 if(amount!=0) {
			 balance=balance+amount;
			 pre_trans=amount;
		 }
		 else {
			 
			 System.out.println("You dont have enough amountto deposit!");
		 }
	 }
	 void withdraw(int amount) {
		 if(amount!=0) {
			 balance=balance-amount;
			 pre_trans=-amount;
		 }
		 else
		 {
			 System.out.println("No amount present to withdraw!");
		 }
	 }
	 void get_pre_trans() {
		 if(pre_trans>0) {
			 System.out.println("Deposit : "+pre_trans);
		 }
		 else if(pre_trans<0) {
			 System.out.println("Withdraw : "+pre_trans);
		 }
		 else
		 {
			 System.out.println("No previous transaction");
		 }
	 }
	 void show_menu(){
		 
		 char option;
		 Scanner sc=new Scanner(System.in);
		 do {
			 
			 System.out.println("A: Check Balance");
			 System.out.println("B: Deposit");
			 System.out.println("C: Withdraw");
			 System.out.println("D: Check the previous transaction");
			 System.out.println("E: exit");
			 System.out.println("Choose an option:");
			 option= sc.next().charAt(0);
		 
		 switch(option) {
		 case 'A':
			 System.out.println("Your balance is: "+balance);
			 break;
		 case 'B':
			 System.out.println("Enter amount to deposit: ");
			 int amount1=sc.nextInt();
			 deposit(amount1);
			 break;
		 case 'C':
			 System.out.println("Enter amount to withdraw: ");
			 int amount2=sc.nextInt();
			 withdraw(amount2);
			 break;
		 case 'D':
			 System.out.println("Your previous transaction was: ");
			 get_pre_trans();
			 break;
		 case 'E':
			 break;}
		 
	 }while(option!='E');
	 
		 
	 }
			 
}
