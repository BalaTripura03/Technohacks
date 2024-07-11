# Technohacks
CURRENCY CONVERTER
class CurrencyConverter:
    def __init__(self):
        # Pre-defined exchange rates (as of 2022-01-01)
        self.exchange_rates = {
            "USD": {"USD": 1.0, "EUR": 0.88, "GBP": 0.74, "JPY": 115.45, "INR": 75.23},
            "EUR": {"USD": 1.14, "EUR": 1.0, "GBP": 0.84, "JPY": 131.21, "INR": 85.45},
            "GBP": {"USD": 1.35, "EUR": 1.19, "GBP": 1.0, "JPY": 155.78, "INR": 98.21},
            "JPY": {"USD": 0.0087, "EUR": 0.0076, "GBP": 0.0064, "JPY": 1.0, "INR": 0.63},
            "INR": {"USD": 0.013, "EUR": 0.012, "GBP": 0.010, "JPY": 1.59, "INR": 1.0}
        }

    def convert_currency(self, amount, from_currency, to_currency):
        if from_currency in self.exchange_rates and to_currency in self.exchange_rates[from_currency]:
            rate = self.exchange_rates[from_currency][to_currency]
            converted_amount = amount * rate
            return converted_amount
        else:
            print("Invalid currencies.")
            return None

# Example usage
converter = CurrencyConverter()

amount = float(input("Enter the amount: "))
from_currency = input("Enter the source currency (e.g., USD): ").upper()
to_currency = input("Enter the target currency (e.g., EUR): ").upper()

converted_amount = converter.convert_currency(amount, from_currency, to_currency)
if converted_amount is not None:
    print(f"{amount} {from_currency} is equivalent to {converted_amount} {to_currency}")
