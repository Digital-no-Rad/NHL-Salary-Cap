# NHL Salary Cap Analysis
# Step-by-step calculations with U.S. federal + state taxes and Canadian combined taxes

# U.S. federal tax rate
us_federal_tax = 0.37  # 37% U.S. federal tax for high-income earners

# State tax rates for U.S. regions
state_tax_rates = {
    "No State Income Tax": 0.0,    # Florida, Texas, Nevada, Washington, Tennessee
    "Low-Tax States": 0.04,        # Colorado, Arizona, Pennsylvania, Ohio
    "Moderate-Tax States": 0.05,   # Illinois, Michigan
    "High-Tax States": 0.08,       # New York, New Jersey, Minnesota
    "Very High-Tax (California)": 0.13  # California
}

# Combined federal + provincial tax rates for Canadian provinces
canada_tax_rates = {
    "Ontario": 0.4616,     # Toronto, Ottawa
    "Quebec": 0.5875,      # Montreal
    "Alberta": 0.43,       # Calgary, Edmonton
    "British Columbia": 0.535  # Vancouver
}

# Function to calculate U.S. take-home pay with federal + state taxes
def calculate_us_take_home(salary, federal_tax, state_tax):
    combined_tax_rate = federal_tax + state_tax
    take_home = salary * (1 - combined_tax_rate)
    return take_home

# Function to calculate Canadian take-home pay with combined tax rates
def calculate_canadian_take_home(salary, combined_tax_rate):
    take_home = salary * (1 - combined_tax_rate)
    return take_home

# Test case for U.S. regions
salary = 10_000_000  # Example salary of $10 million
for region, state_tax in state_tax_rates.items():
    take_home = calculate_us_take_home(salary, us_federal_tax, state_tax)
    print(f"Take-home pay in {region}: ${take_home:,.2f}")

# Test case for Canadian provinces
for province, combined_tax_rate in canada_tax_rates.items():
    take_home = calculate_canadian_take_home(salary, combined_tax_rate)
    print(f"Take-home pay in {province}: ${take_home:,.2f}")
