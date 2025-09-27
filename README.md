# Inheritance-I-
#Design a class Item having a members item_no and Item_name.Create a derived class Price having members quantity and 
# unit_price. Define appropriate constructor in both the classes to intialize the members. Calculate total price and display

class Item:
    def __init__(self,item_no,item_name):
        self.item_no = item_no
        self.item_name = item_name
    def display(self):
        print("Item No:",self.item_no)
        print("Item Name:",self.item_name)
class Price(Item):
    def __init__(self,item_no, item_name,quantity,unit_price):
        super().__init__(item_no,item_name)
        self.quantity = quantity 
        self.unit_price = unit_price
    def total_price(self):
        return self.quantity * self.unit_price
        
    def display_with_price(self):
        self.display()
        print("Quantity:",self.quantity)
        print("Unit Price:",self.unit_price)
        print("Total Price:",self.total_price())

p = Price(item_no = 111,item_name = "Book",quantity = 4,unit_price = 200)
p.display_with_price()


#Program to create a class Calculator that has methods to perform add, sub,mul, div
class Calculator:
    def add(self, a,b):
        return a + b

    def subtract(self, a, b):
        return a - b

    def multiply(self, a, b):
        return a * b

    def divide(self, a, b):
        if b != 0:
            return a / b
        else:
            return "Division by zero not allowed"

calc = Calculator()

print("====Simple Calculator====")
print("Choose operation:")
print("1.Addition")
print("2.Subtraction")
print("3.Multiplication")
print("4.Division")

choice = int(input("Enter your choice(1-4):"))

a = float(input("Enter first number:"))
b = float(input("Enter second number:"))

if choice == 1:
    print(f"Result:{a} + {b} = {calc.add(a, b)}")
elif choice == 2:
    print(f"Result:{a} - {b} = {calc.subtract(a, b)}")
elif choice == 3:
    print(f"Result:{a} * {b} = {calc.multiply(a, b)}")
elif choice == 4:
    print(f"Result:{a} / {b} = {calc.divide(a, b)}")
else:
    print("Invalid choice. Select from the list")
