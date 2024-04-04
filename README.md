"" Create a Account class with methods"""

class Account:
    """Creating an Account class with methods"""
    def __init__(self, balance, interest):
        self.balance = balance
        self.interest = interest

    # This method sets the balance of the account.
    def set_balance(self, balance):
        """Sets the balance for the for the account"""
        self.balance = balance

    # The method sets the interest gained for the account.
    def set_interest(self, interest):
        """Sets the interest gained for the the account"""
        self.interest = interest

        # Import the create_cd_account and create_savings_account functions
from cd_account import create_cd_account
from savings_account import create_savings_account

# Define the main function
def main():
    """This function prompts the user to enter the savings and cd account balance, interest rate,
    and the length of months to determine the interest gained.
    It displays the interest earned on the savings and CD accounts and updates the balances.
    """
    # Prompt the user to set the savings balance, interest rate, and months for the savings account.
    savings_balance = float(input("what is your savings account balance?"))
    savings_interest_rate = float(input("what is your interest rate?"))
    savings_maturity = int(input("what is the maturity of your account?"))

    # Call the create_savings_account function and pass the variables from the user.
    updated_savings_balance, interest_earned = create_savings_account(savings_balance, savings_interest_rate, savings_maturity)

    # Print out the interest earned and updated savings account balance with interest earned for the given months.
    print("interest earned", interest_earned)
    print("savings maturity", savings_maturity)
    print ("updated_savings_balance", updated_savings_balance)
    # Prompt the user to set the CD balance, interest rate, and months for the CD account.
    cd_balance = float(input("what is your cd balance?"))
    cd_interest_rate = float(input("what is your interest rate?"))
    cd_maturity = int(input("what is the maturity of your account?"))


    # Call the create_cd_account function and pass the variables from the user.
    updated_cd_balance, interest_earned = create_cd_account(cd_balance, cd_interest_rate, cd_maturity)

    # Print out the interest earned and updated CD account balance with interest earned for the given months.
    print("interest earned", interest_earned)
    print("cd maturity", cd_maturity)
    print("updated_cd_balance", updated_cd_balance)

if __name__ == "__main__":
    main()
"""Import the Account class from the Account.py file."""
# ADD YOUR CODE HERE
from Account import Account
def create_cd_account(balance, interest_rate, months):
    """Creates a CD account, calculates interest earned, and updates the account balance.

    Args:
        balance (float): The initial CD account balance.
        interest_rate (float): The APR interest rate for the CD account.
        months (int): The length of months for the CD.

    Returns:
        float: The updated CD account balance after adding the interest earned.
        And returns the interest earned.
    """
    # Create an instance of the `Account` class and pass in the balance and interest parameters.
    #  Hint: You need to add the interest as a value, i.e, 0.
    cd_account = Account(balance, 0)

    # Calculate interest earned
    interest_earned = balance * (interest_rate/100 * months/12)

    # Update the CD account balance by adding the interest earned
    updated_balance = balance + interest_earned

    # Pass the updated_balance to the set balance method using the instance of the CDAccount class.
    cd_account.set_balance(updated_balance)

    # Pass the interest_earned to the set interest method using the instance of the CDAccount class.
    cd_account.set_interest(interest_earned)

    # Return the updated balance and interest earned.
    return updated_balance, interest_earned
"""Import the Account class from the Account.py file."""
# ADD YOUR CODE HERE
from Account import Account
# Define a function for the Savings Account
def create_savings_account(balance, interest_rate, months):
    """Creates a savings account, calculates interest earned, and updates the account balance.

    Args:
        balance (float): The initial savings account balance.
        interest_rate (float): The APR interest rate for the savings account.
        months (int): The length of months to determine the amount of interest.

    Returns:
        float: The updated savings account balance after adding the interest earned.
        And returns the interest earned.
    """
    # Create an instance of the `Account` class and pass in the balance and interest parameters.
    #  Hint: You need to add the interest as a value, i.e, 0.
    
    savings_account = Account(balance, 0)
    # Calculate interest earned
     
    interest_earned = balance * (interest_rate/100 * months/12)
    # Update the savings account balance by adding the interest earned
    

    updated_balance = balance + interest_earned
    # Pass the updated_balance to the set balance method using the instance of the SavingsAccount class.
    
    savings_account.set_balance(updated_balance)
    # Pass the interest_earned to the set interest method using the instance of the SavingsAccount class.
    savings_account.set_interest(interest_earned)
    
    # Return the updated balance and interest earned.
    return updated_balance, interest_earned
