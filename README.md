# Exceptions
def withdraw_money(balance, amount):
    try:
        if amount <= 0:
            raise ValueError("Amount must be positive!")  # Simulate invalid input
        if amount > balance:
            raise ValueError("Insufficient balance!")     # Simulate insufficient funds
        
        balance -= amount
        print(f"Withdrew ${amount}. Remaining balance: ${balance}")
    
    except ValueError as e:  # Catches ValueError exceptions
        print(f"Error: {e}")
    
    else:
        print("Transaction successful!")  # Runs if no exception occurs
    
    finally:
        print("Thank you for using our ATM!")  # Always runs

# Test cases
print("--- Case 1: Valid withdrawal ---")
withdraw_money(1000, 500)  # Successful

print("\n--- Case 2: Insufficient balance ---")
withdraw_money(1000, 1500)  # Fails

print("\n--- Case 3: Invalid input ---")
withdraw_money(1000, -100)  # Fails
