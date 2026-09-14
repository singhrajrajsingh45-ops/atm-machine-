# atm-machine-
learn basic code of atm in pytnon .
<br>
Author of this code is raj Singh .





import time

balance = 50000

pin = 9090


print("""
           
          🙏  WELCOME TO HDFC ATM MACHINE  🙏
           
        Balance Check                   Enter  →  0
        Minimum Balance Check           Enter  →  1
        Withdraw                        Enter  →  2
        Deposit                         Enter  →  3
        Exit                            Enter  →  4

  🔒 Password Protected

""")
print("\n🏧 Inserting your card...")
time.sleep(1.5)
print("🧑‍💻 Processing your data...")
time.sleep(1.5)


while True:
    option = input("\nChoose an option (0-4): ")

    if option == "0":
        enterPIN = int(input("Enter your PIN: "))
        print("🔒 Verifying PIN...")
        time.sleep(1)
        if enterPIN == pin:
         print(f"✅ Your current balance is: ₹{balance}")
         print(" THAMK YOU FOR USING HDFC ATM MACHINE ")
    
         break
    elif option == "1":
        if balance < 1000:
            print("⚠️ Your balance is below the minimum required balance of ₹1000.")
            print(" THAMK YOU FOR USING HDFC ATM MACHINE ")
    
        else:
            print("✅ Your balance meets the minimum requirement.")

            
    
    elif option == "2": 
        if balance > 1000:
            print(f"✅ You are eligible to withdraw money.enter the pin to continue")
            enterPIN = int (input("enter the pin :"))
            print("\n🔒 Verifying PIN...")
            time.sleep(1)

            if enterPIN == pin:
                withdraw_amount = int(input("Enter the amount to withdraw: ₹"))
                if withdraw_amount <= balance:
                    print("Processing your withdrawal...")
                    time.sleep(2)
                    print(f"\n✅ Withdrawal successful.\n\n New balance: ₹{balance - withdraw_amount}")

                    print(" \nTHAMK YOU FOR USING HDFC ATM MACHINE ")
                    break
                else:
                    print("⚠️ Insufficient funds for this withdrawal or worng password ")
            if enterPIN != pin:
                print("⚠️ Incorrect PIN. Transaction cancelled.")
                

    elif option == "3": 
        enterPIN = int(input("Enter your PIN: "))
        print("\n🔒 Verifying PIN...")
        time.sleep(1)
        
        if enterPIN == pin:
            deposit_amount = int(input("Enter the amount to deposit: ₹"))
            balance += deposit_amount
            print(f"\n✅ Deposit successful. New balance: ₹{balance}\n")
            print(" THAMK YOU FOR USING HDFC ATM MACHINE ")
    
        if enterPIN != pin:
            print("⚠️ Incorrect PIN. enter the correct pin to continue.")  
            break  

    elif option == "4":
        print("Thank you for using HDFC ATM. Goodbye!")
        break
    else:
        print("⚠️ Invalid option. Please choose a valid option (0-4).")

    
