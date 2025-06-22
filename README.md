# Kirthi-execption-handling-
# Custom Exception
class NegativeNumberError(Exception):
    def __init__(self, message="Negative number is not allowed!"):
        self.message = message
        super().__init__(self.message)

def perform_operations():
    try:
        # Input value
        num = int(input("Enter a number: "))

        # Raise custom exception if number is negative
        if num < 0:
            raise NegativeNumberError()

        # ZeroDivisionError handling
        result = 100 / num
        print(f"Result of 100 / {num} = {result}")

        # FileNotFoundError handling
        with open("sample.txt", "r") as file:
            content = file.read()
            print("File content:\n", content)

    except ZeroDivisionError:
        print("❌ Error: Division by zero is not allowed.")

    except ValueError:
        print("❌ Error: Invalid input. Please enter a valid integer.")

    except FileNotFoundError:
        print("❌ Error: File not found.")

    except NegativeNumberError as e:
        print(f"❌ Custom Error: {e}")

    finally:
        print("✅ Finished execution of try-except-finally block.\n")

# Call the function
perform_operations()
