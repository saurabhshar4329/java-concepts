
class p{
  public static void main(String[] args) {
    bank b1 = new bank();
    b1.setAccNo(25);
    b1.setAccBal(500);
    b1.deposit(500);
    b1.showDetails();
  }
}

interface payment{
  void paymentProcess();
  void showDetails();
  
}

class bank implements payment{

  private int accNo;
  private int accBal;

  //Setter
  public void setAccNo(int accNo){
    this.accNo = accNo;
  }
  public void setAccBal(int accBal){
    this.accBal = accBal;
  }

  //getter
  public int getAccNo(){
    return this.accNo;
  }
  public int getAccBal(){
    return this.accBal;
  }

  public void deposit(int amount){
    if(amount > 0){
      accBal += amount;
      System.out.println("Deposit of money is successfully completed");
    }
    else{
      System.out.println("Invalid Entry...");
    }
  }
  public void withdraw(int amount){
    if(amount > 0 && amount <= accBal ){
      accBal -= amount;
      System.out.println("withdraw is successful");
    }
    else{
      System.out.println("Invalid Entry...");
    }
  }


  @Override
  public void paymentProcess() {
    System.out.println("the amount of withdraw/ deposit is : "+ getAccBal());
  }
  
  @Override
  public void showDetails() {   
    System.out.println("Account details :- ");
    System.out.println("Account number : "+ getAccNo());
    System.out.println("Account balance : "+ getAccBal());
    
  }

}