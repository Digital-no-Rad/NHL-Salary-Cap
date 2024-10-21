# NHL-Salary-Cap.py
To devise a more fair salary cap tax system based on state/provincial and federal taxes. 

# NHL Salary Cap Analysis
# Step-by-step calculations starting from the basics

# Step 1: Initial Setup for Tax Rates (U.S. and Canada)

# Define a dictionary for U.S. federal tax and placeholder for state taxes
us_federal_tax = 0.37  # 37% U.S. federal tax for high-income earners
canada_federal_tax = 0.33  # 33% Canada federal tax for high-income earners

# Placeholder: Provincial and State Taxes (to be added step by step)

# Step 2: Function to calculate take-home pay
def calculate_take_home(salary, tax_rate):
    """
    Calculates take-home pay after applying tax.
    :param salary: Player's total salary
    :param tax_rate: Combined federal + state/provincial tax rate
    :return: Take-home pay after tax
    """
    take_home = salary * (1 - tax_rate)
    return take_home

# Test case for step-by-step calculation
salary = 10_000_000  # Example salary of $10 million
print(f"Take-home pay with U.S. federal tax: ${calculate_take_home(salary, us_federal_tax):,.2f}")

