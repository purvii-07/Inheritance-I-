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
