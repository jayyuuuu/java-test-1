# java-test-1


Test Paper – 1
Core Java

 

Question -1:


// Online Java Compiler
// Use this editor to write, compile and run your Java code online

class Rectangle {
    
    double length;
    double width;
    public void setRectangle(double x, double y){
      length = x;
      width = y;
    }
    public double getArea(){
        return (length*width);
    }
}

class Box extends Rectangle{
    
    double height;
    
    public void setBox(double x, double y, double z){
        length = x;
        width =y;
        height =z;
    }
    
    public double getVolume(){
        return (length*width*height);
    }
    
    
    
    public static void main(String[] args) {
        Box b = new Box();
        b.setBox(2,3,4);
        b.setRectangle(5,10);
        System.out.println(b.getVolume());
        System.out.println(b.getArea());
    }
}





Q2. All the banks operating in India are controlled by RBI. RBI has set a well defined guideline (e.g. minimum interest rate, minimum balance allowed, maximum withdrawal limit etc) which all banks must follow. For example, suppose RBI has set minimum interest rate applicable to a saving bank account to be 4% annually; however, banks are free to use 4% interest rate or to set any rates above it.

Write a JAVA program to implement bank functionality in the above scenario and demonstrate the dynamic polymorphism concept. Note: Create few classes namely Customer, Account, RBI (Base Class) and few derived classes (SBI, ICICI, PNB etc). Assume and implement required member variables and functions in each class.


/******************************************************************************

                            Online Java Compiler.
                Code, Compile, Run and Debug java program online.
Write your code in this editor and press "Run" button to execute it.

*******************************************************************************/

// Online Java Compiler
// Use this editor to write, compile and run your Java code online


/*package whatever //do not write package name here */


import java.util.Scanner;

class RBI{
    int withLimit,n;
    double A,P,r;
    float t;
    long avg,tot,mb;

    int setWithdrawalLimit() {
        Scanner inp = new Scanner(System.in);
                withLimit = 4000;
        return withLimit;
    }

    double setInterestRate() {
        A=(P+r)/n*t;
        return A;
    }
}

class SBI extends RBI{ 
    double setInterestRate() {
        A=P*(1+r/n)+n*t;
        return A;
    }
 }

class ICICI extends RBI{ 
    double setInterestRate() {
        A=(P*r)/n+t;
        return A;
    }

    int setWithdrawalLimit() {
        withLimit=7000;
        return withLimit;
    }
}

public class Main { 
    public static void main(String args[]) {
        SBI sbi = new SBI();
        ICICI icici = new ICICI();
        sbi.P=9.433;
        sbi.r=7.42;
        sbi.n=5;
        sbi.t=7;
        Double sbiInt=sbi.setInterestRate();
        System.out.println("SBI interest rate is:"+sbiInt);
        int iciciWL= icici.setWithdrawalLimit();
        System.out.println("ICICI withdraw limit is:"+iciciWL);
    }
}




Que 3 
A boy has his money deposited $1000, $1500 and $2000 in banks-Bank A, Bank B and Bank C respectively. We have to print the money deposited by him in a particular bank.
Create a class 'Bank' with a method 'getBalance' which returns 0. Make its three subclasses named 'BankA', 'BankB' and 'BankC' with a method with the same name 'getBalance' which returns the amount deposited in that particular bank. Call the method 'getBalance' by the object of each of the three banks.



Ans:
// Online Java Compiler
// Use this editor to write, compile and run your Java code online

class Bank {
	int getBalance() {
		return 0;
	}
}
class BankA extends Bank{
	int getBalance(int balance) {
		return balance;
	}
}
class BankB extends Bank{
	int getBalance(int balance) {
		return balance;
	}
}
class BankC extends Bank{
	int getBalance(int balance) {
		return balance;
	}
}

public class Main{

	public static void main(String[] args) {
		BankA obj1 = new BankA();
		BankB obj2 = new BankB();
		BankC obj3 = new BankC();
		
		System.out.println("$" +obj1.getBalance(1000));

		System.out.println("$" +obj2.getBalance(1500));

		System.out.println("$" +obj3.getBalance(2000));
		
	}

}





Q5 Question - you are working with an airline company 
•	You are in the luggage check-in department and as per rules, you can allow 15kg per customer.
•	So now more than 15kg of weight is an abnormal condition for us or in other words its an exception
•	This is our logic-based exception, so you have to  create our custom exception WeightLimitExceeded 
•	Use this exception into main application to check the environment. 


Ans:
/******************************************************************************

                            Online Java Compiler.
                Code, Compile, Run and Debug java program online.
Write your code in this editor and press "Run" button to execute it.

*******************************************************************************/

// Online Java Compiler
// Use this editor to write, compile and run your Java code online


/*package whatever //do not write package name here */


class WeightLimitExceeded extends Exception{
    WeightLimitExceeded(int x){
        System.out.print(Math.abs(15-x)+" kg : ");
    }
}


class Main {
    void validWeight(int weight) throws WeightLimitExceeded{
        if(weight>15)
            throw new WeightLimitExceeded(weight);
        else
            System.out.println("Weight is less than 15kg");
    }
    
      public static void main (String[] args) {
        Main m1=new Main();
        Scanner in=new Scanner(System.in);
        for(int i=0;i<2;i++){
            try{
                m1.validWeight(in.nextInt());
            }catch(WeightLimitExceeded e){
                System.out.println(e);
            }
        }
        
	}
}





Que 4:  
The Java class called Holiday is started below. An object of class Holiday represents a holiday during the year. This class has three instance variables:

 ● name, which is a String representing the name of the holiday 
● day, which is an intre presenting the day of the month of the holiday
 ● month, which is a String representing the month the holiday is in 
public class Holiday
 { private String name; 
private int day; 
private String month; // your code goes here}






