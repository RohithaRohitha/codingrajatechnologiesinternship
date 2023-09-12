# Initialize variables and data structures

budget = 0

expenses = []

income = []

expense_categories = {}

 

while True:

    # Display menu and get user choice

    print("Budget Tracker Menu:")

    print("1. Add Expense")

    print("2. Add Income")

    print("3. View Budget")

    print("4. View Expense Analysis")

    print("5. Exit")

    choice = input("Enter your choice: ")

 

    if choice == "1":

        # Add Expense

        category = input("Enter expense category: ")

        amount = float(input("Enter expense amount: "))

        expenses.append({"category": category, "amount": amount})

        budget -= amount

        if category in expense_categories:

            expense_categories[category] += amount

        else:

            expense_categories[category] = amount

        print("Expense added successfully.")

 

    elif choice == "2":

        # Add Income

        amount = float(input("Enter income amount: "))

        income.append(amount)

        budget += amount

        print("Income added successfully.")

 

    elif choice == "3":

        # View Budget

        print(f"Current Budget Balance: ${budget}")

 

    elif choice == "4":

        # View Expense Analysis

        print("Expense Analysis:")

        for category, amount in expense_categories.items():

            print(f"{category}: ${amount}")

 

    elif choice == "5":

        # Exit and save data to a file (e.g., JSON)

        # You can implement the data persistence part here

        break

 

    else:

        print("Invalid choice. Please select a valid option.")