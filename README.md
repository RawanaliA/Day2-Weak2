# Day2-Weak2
//THE Main src Code
public class Main {
    public static void main(String[] args) {
        Account a=new Account("369","Rawan");
        Account a1=new Account("111","Ali",300);
        System.out.println("your Id is :"+a1.getId()+"\nYour name is :"+a1.getName()+"\nyour balance is :"+a1.getBalance());
       a.cridet(2000);
       a1.cridet(2000);
       a1.debit(1000);
        System.out.println(""+a.getBalance());
        System.out.println(""+a1.getBalance());
       a.transferTo(a1,500);
        a1.transferTo(a,200);

        System.out.println(""+a.toString());
        System.out.println(""+a1.toString());

//The Employee
        Employee e=new Employee("77","Rawan Ali",16000);
        System.out.println("your Id is :"+e.getId()+"\nYour name is :"+e.getName()+"\nyour Salary is :"+e.getSalary());
        System.out.println("Your annualSalary is: "+e.getAnnualSalary());
        System.out.println("The RasiedSalary on your Salary :"+e.rasiedSalary());
        System.out.println(""+e.toString());
    }
}
//The Account Class
import java.util.Scanner;

public class Account {
    private String id;
    private String name;
    private int balance = 0;

//public int amount;
 public Account(){
//     اجرب اط
 }
    public Account(String id,String name) {
     this.id=id;
     this.name=name;
    }public Account(String id,String name,int balance){
        this.id=id;
        this.name=name;
        this.balance=balance;
    }

    public String getId() {
        return id;
    }

    public String getName() {
        return name;
    }

    public int getBalance() {
        return balance;
    }
    //
    public void cridet(int amount) {
       this.balance=balance+amount;
        System.out.println("Your balance now is "+balance);
    }
    public void debit(int amount){
     if(amount<balance){
        balance=balance-amount;
        System.out.println(name+" The diept is Done  "+balance);}
     else {
         System.out.println("After debit your balance now is" +amount);
     }
 }

    public void transferTo(Account another, double amount) {
        if(this.balance <amount) {
            System.err.println("Transaction fails!");
        }
        else {
            this.balance -= amount;
            another.balance+=amount;
            System.out.println("Transaction Successful");
            System.out.println("Account of "+this.name +" has "+this.balance+" Ryalis");
            System.out.println("Account of  "+another.name +" has "+another.balance+" Ryalis");


        }
    }

}
//The Employee class
public class Employee {
    private  String id;
    private String name;
    private int salary;
    public int annualSalary;
    private double rasiedSalary;
    public Employee(String id, String name, int salary) {
        this.id = id;
        this.name = name;
        this.salary = salary;
    }

    public String getId() {
        return id;
    }

    public String getName() {
        return name;
    }

    public int getSalary() {
        return salary;
    }

    public int getAnnualSalary() {
        annualSalary=12*salary;
        return annualSalary;
    }

    public double rasiedSalary(){
        rasiedSalary=salary*10/100;
        return rasiedSalary;
    }
}
