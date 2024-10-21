# NHL Salary Cap Analysis
# Step-by-step calculations starting from federal tax

# Step 1: Federal Taxes Only (U.S. and Canada)

# Define federal tax rates
us_federal_tax = 0.37  # 37% U.S. federal tax for high-income earners
canada_federal_tax = 0.33  # 33% Canada federal tax for high-income earners

# Function to calculate take-home pay with federal tax only
def calculate_take_home_federal(salary, federal_tax_rate):
    """
    Calculates take-home pay after applying federal tax.
    :param salary: Player's total salary
    :param federal_tax_rate: Federal tax rate (U.S. or Canada)
    :return: Take-home pay after federal tax
    """
    take_home = salary * (1 - federal_tax_rate)
    return take_home

# Test case for step-by-step calculation
salary = 10_000_000  # Example salary of $10 million
print(f"Take-home pay with U.S. federal tax: ${calculate_take_home_federal(salary, us_federal_tax):,.2f}")
print(f"Take-home pay with Canada federal tax: ${calculate_take_home_federal(salary, canada_federal_tax):,.2f}")


