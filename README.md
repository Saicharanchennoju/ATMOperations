class ATMOperations {
	double balance;
	String password="Sai123";
	boolean checkPassword(String Password) {
		boolean checkPass=false;
		if(this.password.equals(Password)) {
			   checkPass=true;
		}
		return checkPass;
			}
       double checkBalance() {
    	   return balance;
       }
       boolean withDrawAmount(double amount){
    	   boolean succuss=false;
    	  if(balance>=amount) {
    		  balance-=amount;
    		  succuss=true;
    	  }
    	  return succuss;
       }
       boolean depositeAmount(double amount) {
    	   boolean succuss=false;
    	   if(amount>0) {
    		   balance+=amount;
    		   succuss=true;
    	   }
    	   return succuss;
       }
	public static void main(String[] args) {
		Scanner sc=new
				Scanner(System.in);
		ATMOperations ob1=new ATMOperations();
		System.out.println("Enter the your Password");
		String pass=sc.nextLine();
		if(!ob1.checkPassword(pass)) {
           System.out.println("Invalid Password... Access Denied");
           return;
		}
		boolean exit=false;
		while(!exit){
			System.out.println("1 Check Balance");
			System.out.println("2 Deposite Amount");
			System.out.println("3 Withdraw Amount");
			System.out.println("4 Exit");
			int op=sc.nextInt();
			switch(op) {
			case 1:System.out.println("Your Current Balance="+ob1.checkBalance());break;
			case 2:System.out.println("Enter Amount to Deposite:");
			    double am1=sc.nextDouble();
			    if(ob1.depositeAmount(am1)) {
			    	System.out.println(am1+"is successfully deposited..");
			    }else {
			    	System.out.println(am1+"invalid amount");
			    }
			    break;
			case 3:System.out.println("Enter an amount to withdraw:");
			    double am2=sc.nextDouble();
			    if(ob1.withDrawAmount(am2)) {
			    	System.out.println(am2+"is succussfully Withdraw");
			    }else {
			    	System.out.println("Insufficent Balance");
			    }
			    break;
			case 4:exit=true;
			       System.out.println("Thank You for using Our Services");
			       break;
			    }
			}
		}
	}
