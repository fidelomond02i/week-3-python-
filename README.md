# week-3-python-
Create a function named calculate_discount(price, discount_percent) that calculates the final price after applying a discount. The function should take the original price (price) and the discount percentage (discount_percent) as parameters. If the discount is 20% or higher, apply the discount; otherwise, return the original price.
Using the calculate_discount function, prompt the user to enter the original price of an item and the discount percentage. Print the final price after applying the discount, or if no discount was applied, print the original price.

def calculate_discount(price, discount_percent):
    """
    Calculates the final price after applying a discount.

    Args:
        price (float): The original price of the item.
        discount_percent (float): The discount percentage (e.g., 20 for 20%).

    Returns:
        float: The final price after applying the discount, or the original
               price if the discount is less than 20%.
    """
    if discount_percent >= 20:
        discount_amount = price * (discount_percent / 100)
        final_price = price - discount_amount
        return final_price
    else:
        return price

# Prompt the user for input
try:
    original_price = float(input("Enter the original price of the item: "))
    discount_percentage = float(input("Enter the discount percentage (e.g., 20 for 20%): "))

    # Calculate the final price using the function
    final_price_after_discount = calculate_discount(original_price, discount_percentage)

    # Print the result
    if final_price_after_discount != original_price:
        print(f"Final price after applying discount: ${final_price_after_discount:.2f}")
    else:
        print(f"No discount applied. Original price: ${original_price:.2f}")

except ValueError:
    print("Invalid input. Please enter numeric values for price and discount percentage.")
except Exception as e:
    print(f"An error occurred: {e}")
