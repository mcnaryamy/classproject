def convert_temperature():
    while True:
        user_input = input("Enter temperature (or type 'quit' to exit): ")
        if user_input.lower() == 'quit':
            break
        
        try:
            # Split the input into value and unit
            value, unit = user_input.split()
            value = float(value)  # Attempt to convert to float
            
            if unit.lower() == 'celsius' or unit.lower() == 'c':
                # Convert Celsius to Fahrenheit
                fahrenheit = (9/5) * value + 32
                print(f"{value}°C is {fahrenheit:.2f}°F")
            elif unit.lower() == 'fahrenheit' or unit.lower() == 'f':
                # Convert Fahrenheit to Celsius
                celsius = (5/9) * (value - 32)
                print(f"{value}°F is {celsius:.2f}°C")
            else:
                print("Invalid unit. Please enter 'Celsius' or 'Fahrenheit'.")
        
        except ValueError:
            print("Invalid input. Please enter a numeric value followed by the unit (Celsius or Fahrenheit).")

if __name__ == "__main__":
    convert_temperature()
