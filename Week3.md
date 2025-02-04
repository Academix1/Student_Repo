## DayWise Schedule of Python

---

### **Day 1: Variables and Operators**  

```python
# Python Operators

# 1. Arithmetic Operators
# Used to perform mathematical operations

a = 10
b = 5
print("Arithmetic Operators:")
print("a + b =", a + b)  # Addition
print("a - b =", a - b)  # Subtraction
print("a * b =", a * b)  # Multiplication
print("a / b =", a / b)  # Division
print("a // b =", a // b)  # Floor Division
print("a % b =", a % b)  # Modulus
print("a ** b =", a ** b)  # Exponentiation

# 2. Comparison Operators
# Used to compare two values

print("\nComparison Operators:")
print("a == b:", a == b)  # Equal to
print("a != b:", a != b)  # Not equal to
print("a > b:", a > b)  # Greater than
print("a < b:", a < b)  # Less than
print("a >= b:", a >= b)  # Greater than or equal to
print("a <= b:", a <= b)  # Less than or equal to

# 3. Logical Operators
# Used to combine conditional statements

x = True
y = False
print("\nLogical Operators:")
print("x and y:", x and y)  # AND
print("x or y:", x or y)  # OR
print("not x:", not x)  # NOT

# 4. Assignment Operators
# Used to assign values to variables

c = 20
print("\nAssignment Operators:")
c += 5  # c = c + 5
print("c += 5:", c)
c -= 5  # c = c - 5
print("c -= 5:", c)
c *= 5  # c = c * 5
print("c *= 5:", c)
c /= 5  # c = c / 5
print("c /= 5:", c)
c //= 5  # c = c // 5
print("c //= 5:", c)
c %= 5  # c = c % 5
print("c %= 5:", c)
c **= 5  # c = c ** 5
print("c **= 5:", c)

# 5. Bitwise Operators
# Used to perform bit-level operations on binary numbers

print("\nBitwise Operators:")
print("a & b =", a & b)  # AND
print("a | b =", a | b)  # OR
print("a ^ b =", a ^ b)  # XOR
print("a ~ b =", ~a)  # NOT
print("a << 1 =", a << 1)  # Left shift
print("a >> 1 =", a >> 1)  # Right shift

# 6. Membership Operators
# Used to test if a value is found within a sequence (like a list, string, or tuple)

lst = [1, 2, 3, 4, 5]
print("\nMembership Operators:")
print("3 in lst:", 3 in lst)  # Checks if 3 is in the list
print("10 not in lst:", 10 not in lst)  # Checks if 10 is not in the list

# 7. Identity Operators
# Used to compare the memory locations of two objects

x = [1, 2, 3]
y = [1, 2, 3]
z = x
print("\nIdentity Operators:")
print("x is y:", x is y)  # Checks if x and y are the same object
print("x is z:", x is z)  # Checks if x and z are the same object
print("x is not y:", x is not y)  # Checks if x and y are not the same object

```
### **Day 1 ATM PROJECT (operators and Variables)**
```python

print("--- User Registration ---")
name = input("Enter your name: ")  
phone = input("Enter your mobile number: ")  
initial_balance = float(input("Enter your initial deposit amount: ₹"))  
pin = input("Set your 4-digit PIN: ")  
print(f"\nRegistration Successful!")
print(f"Name: {name}, Phone: {phone}, Balance: ₹{initial_balance}, PIN: {pin}")

deposit_amount = float(input("Enter amount to deposit: ₹"))
new_balance = initial_balance + deposit_amount  

print(f"Balance after deposit: ₹{new_balance}")

withdraw_amount = float(input("Enter amount to withdraw: ₹"))
post_withdrawal_balance = new_balance - withdraw_amount  

print(f"Balance after withdrawal: ₹{post_withdrawal_balance}")

```

---

### **Day 2: Conditionals and Loops**  

```python
# Conditional Statements
print("Conditional Statements:")

# Using if-elif-else to categorize age
age = 20
if age < 18:
    print("You are a minor.")
elif age >= 18 and age < 60:
    print("You are an adult.")
else:
    print("You are a senior citizen.")

# Loops

# 1. For Loop - Iterates over a range of values
print("\nFor Loop:")
for i in range(5):  # Loop through values 0 to 4
    print(f"For loop iteration {i}")

# 2. While Loop - Executes as long as the condition is True
print("\nWhile Loop:")
count = 0
while count < 3:  # Loop will run as long as count is less than 3
    print(f"While loop count: {count}")
    count += 1  # Increment count

# 3. Break and Continue in a For Loop
print("\nBreak and Continue in For Loop:")
for i in range(5):
    if i == 2:
        continue   # Skip iteration when i equals 2
    print(f"Current number: {i}")

# 4. Break Statement
print("\nBreak Statement Example:")
for i in range(5):
    if i == 3:
        print("Breaking the loop as i equals 3.")
        break  # Exit the loop when i equals 3
    print(f"Current number: {i}")

```

### **Day2 ATM PROJECT (Loops and Conditionals)**

```python
name = str(input("Enter Name: "))
initial_balance = float(input("Enter Your Balance: "))

while initial_balance <= 0:
    print("Balance Should be > than 0")
    initial_balance = float(input("Enter Your Balance: "))

pin = input("Enter Your Pin: ")

while len(pin) != 4 or not pin.isdigit():
    print("Invalid Pin! Enter a 4-digit PIN (Numbers only).")
    pin = input("Enter the PIN: ")

while True:
    print("1. Deposit")
    print("2. Withdrawal")
    print("3. Exit")
    choice = int(input("Enter Your Choice (1/2/3): "))

    if choice == 1:
        deposit = float(input("Enter Your Deposit Amount: "))
        initial_balance += deposit
        print(f"Balance after deposit: ₹{initial_balance}")

    elif choice == 2:
        withdrawal = float(input("Enter Withdrawal Amount: "))

        while withdrawal > initial_balance:
            print("Withdrawal amount should be less than or equal to the available balance.")
            withdrawal = float(input("Enter Withdrawal Amount: "))

        initial_balance -= withdrawal
        print(f"Balance after withdrawal: ₹{initial_balance}")

    elif choice == 3:
        print("Thanks for Visiting!")
        break

    else:
        print("Invalid choice. Please enter 1, 2, or 3.")
```
---

### **Day 3: Functions**  

```python
# Python Functions

# 1. Simple Function - Basic function without parameters or return value
def greet():
    print("Hello! Welcome to Python Functions.")

# 2. Function with Parameters - Function that accepts parameters
def greet_user(name):
    print(f"Hello, {name}! Welcome to Python Functions.")

# 3. Function with Return Value - Function that returns a value
def add(a, b):
    return a + b

# 4. Function with Default Arguments - Function that uses default parameter values
def greet_user_with_default(name="Guest"):
    print(f"Hello, {name}! Welcome to Python Functions.")

# 5. Function with Variable Number of Arguments (Arbitrary Arguments) - Using *args for a variable number of arguments
def calculate_sum(*args):
    return sum(args)

# 6. Function with Keyword Arguments - Using **kwargs for a variable number of keyword arguments
def display_person_info(**kwargs):
    for key, value in kwargs.items():
        print(f"{key}: {value}")

# 7. Recursive Function - A function that calls itself
def factorial(n):
    if n == 0 or n == 1:
        return 1
    else:
        return n * factorial(n - 1)

# 8. Lambda Function - Anonymous function defined using lambda keyword
square = lambda x: x * x

# 9. Nested Function - A function defined inside another function
def outer_function():
    def inner_function():
        return "This is the inner function!"
    return inner_function()

# 10. Function with *args and **kwargs together - Passing both non-keyword and keyword arguments
def display_args_and_kwargs(a, *args, **kwargs):
    print(f"a: {a}")
    print("args:", args)
    print("kwargs:", kwargs)

# Example Usage
if __name__ == "__main__":
    # Simple Function
    greet()

    # Function with Parameters
    greet_user("Alice")

    # Function with Return Value
    result = add(10, 20)
    print(f"Addition result: {result}")

    # Function with Default Arguments
    greet_user_with_default()
    greet_user_with_default("Bob")

    # Function with Arbitrary Arguments
    total_sum = calculate_sum(1, 2, 3, 4, 5)
    print(f"Sum of numbers: {total_sum}")

    # Function with Keyword Arguments
    display_person_info(name="John", age=30, city="New York")

    # Recursive Function
    fact_result = factorial(5)
    print(f"Factorial of 5: {fact_result}")

    # Lambda Function
    print(f"Square of 4 using lambda: {square(4)}")

    # Nested Function
    print(outer_function())

    # Function with *args and **kwargs together
    display_args_and_kwargs(10, 1, 2, 3, name="Alice", age=25)

```
### **Day3 ATM PROJECT (Functions)**

```python
name = input("Enter Name: ")

initial_balance = float(input("Enter Your Balance: "))
while initial_balance <= 0:
    print("Balance should be greater than 0.")
    initial_balance = float(input("Enter Your Balance: "))

pin = input("Set Your PIN (4-digit): ")
while len(pin) != 4 or not pin.isdigit():
    print("Invalid PIN. Enter a 4-digit numeric PIN.")
    pin = input("Set Your PIN (4-digit): ")

def validate_pin(stored_pin, entered_pin):
    return stored_pin == entered_pin

def deposit(balance, damount):
    balance += damount
    return balance

def withdraw(balance, wamount):
    while wamount > balance:
        print("Withdrawal amount should not exceed the current balance.")
        wamount = float(input("Enter a valid Withdrawal Amount: "))
    balance -= wamount
    return balance

# Main Program
while True:
    re_rentered_pin = input("Enter Your PIN: ")
    if validate_pin(pin, re_rentered_pin):
        print(f"Welcome {name}!")
        while True:
            print("\nOptions:")
            print("1. Deposit")
            print("2. Withdraw")
            print("3. Exit")
            choice = input("Enter your choice: ")

            if choice == "1":
                deposit_amount = float(input("Enter the amount to deposit: "))
                initial_balance = deposit(initial_balance, deposit_amount)
                print(f"Your current balance is: {initial_balance}")

            elif choice == "2":
                withdrawal_amount = float(input("Enter the amount to withdraw: "))
                initial_balance = withdraw(initial_balance, withdrawal_amount)
                print(f"Your current balance is: {initial_balance}")

            elif choice == "3":
                print("Goodbye!")
                break

            else:
                print("Invalid choice. Please try again.")
    else:
        print("Incorrect PIN. Please try again.")

```

---

### **Day 4: Collections**  

```python
Here are the four files with the comments removed:

### 1. **Lists.py**

```python
my_list = [1, 2, 3, 4, 5]
print(f"Original List: {my_list}")

print(f"Element at index 2: {my_list[2]}")

print(f"Slice of list [1:4]: {my_list[1:4]}")

my_list[2] = 10
print(f"List after modification: {my_list}")

my_list.append(6)
print(f"List after append: {my_list}")
my_list.insert(2, 7)
print(f"List after insert: {my_list}")

my_list.remove(10)
print(f"List after remove: {my_list}")
removed_item = my_list.pop()
print(f"List after pop: {my_list}, Removed Item: {removed_item}")

print("Looping through the list:")
for item in my_list:
    print(item)

squared_numbers = [x ** 2 for x in my_list]
print(f"Squared Numbers: {squared_numbers}")
```

### 2. **Sets.py**

```python
my_set = {1, 2, 3, 4, 5}
print(f"Original Set: {my_set}")

my_set.add(6)
print(f"Set after add: {my_set}")

my_set.remove(3)
print(f"Set after remove: {my_set}")

another_set = {4, 5, 6, 7}
print(f"Union of sets: {my_set | another_set}")
print(f"Intersection of sets: {my_set & another_set}")
print(f"Difference of sets: {my_set - another_set}")

print("Looping through the set:")
for item in my_set:
    print(item)
```

### 3. **Tuples.py**

```python
my_tuple = (1, 2, 3, 4, 5)
print(f"Original Tuple: {my_tuple}")

print(f"Element at index 3: {my_tuple[3]}")

print(f"Slice of tuple [1:4]: {my_tuple[1:4]}")

new_tuple = my_tuple + (6, 7)
print(f"New Tuple after concatenation: {new_tuple}")

print("Looping through the tuple:")
for item in my_tuple:
    print(item)
```

### 4. **Dictionaries.py**

```python
my_dict = {"name": "John", "age": 30, "city": "New York"}
print(f"Original Dictionary: {my_dict}")

print(f"Value for key 'name': {my_dict['name']}")

my_dict["age"] = 31
print(f"Dictionary after modification: {my_dict}")

my_dict["country"] = "USA"
print(f"Dictionary after adding new key-value pair: {my_dict}")

del my_dict["city"]
print(f"Dictionary after removing 'city': {my_dict}")

print("Looping through the dictionary:")
for key, value in my_dict.items():
    print(f"{key}: {value}")

squared_dict = {x: x**2 for x in range(1, 6)}
print(f"Squared Dictionary: {squared_dict}")

if "name" in my_dict:
    print(f"'name' key exists in the dictionary")
```

### **Day4 ATM PROJECT (Collections)**

```python
name = input("Enter Name: ")
initial_balance = float(input("Enter Your Balance: "))
while initial_balance <= 0:
    print("Balance Should be greater than 0.")
    initial_balance = float(input("Enter Your Balance: "))

pin = input("Set Your PIN (4-digit): ")

while len(pin) != 4 or not pin.isdigit():
    print("Invalid PIN. Enter a 4-digit numeric PIN.")
    pin = input("Set Your PIN (4-digit): ")

def validate_pin(stored_pin, entered_pin):
    return stored_pin == entered_pin

def deposit(balance, damount):
    balance += damount
    return balance

def withdraw(balance, wamount):
    while wamount > balance:
        print("Withdrawal amount should not exceed the current balance.")
        wamount = float(input("Enter a valid Withdrawal Amount: "))
    balance -= wamount
    return balance

transaction_history = []

while True:
    re_rentered_pin = input("Enter Your PIN: ")
    if validate_pin(pin, re_rentered_pin):
        print(f"Welcome {name}!")
        while True:
            print("\nOptions:")
            print("1. Deposit")
            print("2. Withdraw")
            print("3. View Transaction History")
            print("4. Exit")
            choice = input("Enter your choice: ")

            if choice == "1":
                deposit_amount = float(input("Enter the amount to deposit: "))
                initial_balance = deposit(initial_balance, deposit_amount)
                transaction_history.append(
                    {"Type": "Deposit", "Amount": deposit_amount, "Balance": initial_balance}
                )
                print(f"Your current balance is: {initial_balance}")

            elif choice == "2":
                withdrawal_amount = float(input("Enter the amount to withdraw: "))
                initial_balance = withdraw(initial_balance, withdrawal_amount)
                transaction_history.append(
                    {"Type": "Withdraw", "Amount": withdrawal_amount, "Balance": initial_balance}
                )
                print(f"Your current balance is: {initial_balance}")

            elif choice == "3":
                if not transaction_history:
                    print("No transactions available.")
                else:
                    print("\nTransaction History:")
                    for index, transaction in enumerate(transaction_history, start=1):
                        print(f"{index}. {transaction['Type']} - Amount: {transaction['Amount']} - Balance: {transaction['Balance']}")

            elif choice == "4":
                print("Goodbye!")
                break
            else:
                print("Invalid choice. Please try again.")
    else:
        print("Incorrect PIN. Please try again.")
```

---

### **Day 5: Object-Oriented Programming (OOP)**  

```python
# Basic OOP Concepts

class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        print(f"Hello, my name is {self.name} and I am {self.age} years old.")

# Inheritance
class Student(Person):
    def __init__(self, name, age, course):
        super().__init__(name, age)  # Call parent class constructor
        self.course = course

    def study(self):
        print(f"{self.name} is studying {self.course}.")

# Encapsulation
class Employee:
    def __init__(self, name, salary):
        self.name = name
        self.__salary = salary  # Private attribute

    def set_salary(self, salary):
        if salary > 0:
            self.__salary = salary
        else:
            print("Invalid salary")

    def get_salary(self):
        return self.__salary

# Polymorphism
class Dog:
    def speak(self):
        print("Woof!")

class Cat:
    def speak(self):
        print("Meow!")

class AnimalSound:
    def make_sound(self, animal):
        animal.speak()

# Abstraction
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def sound(self):
        pass

class Cow(Animal):
    def sound(self):
        print("Moo!")

class Duck(Animal):
    def sound(self):
        print("Quack!")

# Creating objects
person = Person("Alice", 30)
person.greet()

student = Student("Bob", 20, "Python")
student.greet()
student.study()

employee = Employee("Charlie", 50000)
print(f"{employee.name}'s salary is: {employee.get_salary()}")
employee.set_salary(55000)
print(f"{employee.name}'s updated salary is: {employee.get_salary()}")

dog = Dog()
cat = Cat()

animal_sound = AnimalSound()
animal_sound.make_sound(dog)
animal_sound.make_sound(cat)

cow = Cow()
duck = Duck()

cow.sound()
duck.sound()
```

### **Day5 ATM PROJECT (Classes and Objects)**

```python
class ATM:
    def __init__(self, name, initial_balance, pin):
        self.name = name
        self.balance = initial_balance
        self.pin = pin
        self.transaction_history = []

    def validate_pin(self, entered_pin):
        return self.pin == entered_pin

    def deposit(self, amount):
        self.balance += amount
        self.transaction_history.append(
            {"Type": "Deposit", "Amount": amount, "Balance": self.balance}
        )
        return self.balance

    def withdraw(self, amount):
        while amount > self.balance:
            print("Withdrawal amount should not exceed the current balance.")
            amount = float(input("Enter a valid Withdrawal Amount: "))
        self.balance -= amount
        self.transaction_history.append(
            {"Type": "Withdraw", "Amount": amount, "Balance": self.balance}
        )
        return self.balance

    def view_transaction_history(self):
        if not self.transaction_history:
            print("No transactions available.")
        else:
            print("\nTransaction History:")
            for index, transaction in enumerate(self.transaction_history, start=1):
                print(
                    f"{index}. {transaction['Type']} - Amount: {transaction['Amount']} - Balance: {transaction['Balance']}"
                )

name = input("Enter Name: ")
initial_balance = float(input("Enter Your Balance: "))
while initial_balance <= 0:
    print("Balance Should be greater than 0.")
    initial_balance = float(input("Enter Your Balance: "))

pin = input("Set Your PIN (4-digit): ")
while len(pin) != 4 or not pin.isdigit():
    print("Invalid PIN. Enter a 4-digit numeric PIN.")
    pin = input("Set Your PIN (4-digit): ")

atm = ATM(name, initial_balance, pin)

while True:
    entered_pin = input("Enter Your PIN: ")
    if atm.validate_pin(entered_pin):
        print(f"Welcome {atm.name}!")
        while True:
            print("\nOptions:")
            print("1. Deposit")
            print("2. Withdraw")
            print("3. View Transaction History")
            print("4. Exit")
            choice = input("Enter your choice: ")

            if choice == "1":
                deposit_amount = float(input("Enter the amount to deposit: "))
                atm.deposit(deposit_amount)
                print(f"Your current balance is: {atm.balance}")

            elif choice == "2":
                withdrawal_amount = float(input("Enter the amount to withdraw: "))
                atm.withdraw(withdrawal_amount)
                print(f"Your current balance is: {atm.balance}")

            elif choice == "3":
                atm.view_transaction_history()

            elif choice == "4":
                print("Goodbye!")
                break
            else:
                print("Invalid choice. Please try again.")
    else:
        print("Incorrect PIN. Please try again.")
```

---

### **Day 6: Exception Handling & File Handling**  

```python
# Exception Handling
try:
    x = 10 / 0  # Division by zero
except ZeroDivisionError:
    print("Error: Division by zero occurred!")
finally:
    print("Execution complete.")

# File Handling
# Writing to a file
with open('example.txt', 'w') as file:
    file.write("Hello, this is a test file!\n")
    file.write("File handling in Python is easy.")

# Reading from a file
with open('example.txt', 'r') as file:
    content = file.read()
    print(f"File content: {content}")
```

### **Day6 ATM PROJECT (Exception and FileHandling)**

```python
import random
import json
import os

class ATM:
    def __init__(self, name, initial_balance, pin):
        self.name = name
        self.balance = initial_balance
        self.pin = pin

    def validate_pin(self, entered_pin):
        return self.pin == entered_pin

    def deposit(self, amount):
        self.balance += amount
        self.save_transaction_history("Deposit", amount)
        self.save_account_details()
        return self.balance

    def withdraw(self, amount):
        while amount > self.balance:
            print("Withdrawal amount should not exceed the current balance.")
            amount = float(input("Enter a valid Withdrawal Amount: "))
        self.balance -= amount
        self.save_transaction_history("Withdraw", amount)
        self.save_account_details()
        return self.balance

    def save_transaction_history(self, transaction_type, amount):
        if os.path.exists("transaction_data.json"):
            with open("transaction_data.json", "r") as file:
                transaction_data = json.load(file)
        else:
            transaction_data = {}

        if self.name not in transaction_data:
            transaction_data[self.name] = []

        transaction_data[self.name].append({
            "Type": transaction_type,
            "Amount": amount,
            "Balance": self.balance
        })

        with open("transaction_data.json", "w") as file:
            json.dump(transaction_data, file, indent=4)

    def save_account_details(self):
        if os.path.exists("user_data.json"):
            with open("user_data.json", "r") as file:
                user_data = json.load(file)
        else:
            user_data = {}

        user_data[self.name] = {
            "Balance": self.balance,
            "PIN": self.pin
        }

        with open("user_data.json", "w") as file:
            json.dump(user_data, file, indent=4)

    def get_account_balance(self):
        return self.balance

    def get_transaction_history(self):
        if os.path.exists("transaction_data.json"):
            with open("transaction_data.json", "r") as file:
                transaction_data = json.load(file)
            return transaction_data.get(self.name, [])
        return []


def generate_otp():
    return random.randint(100000, 999999)

def validate_otp(sent_otp):
    entered_otp = int(input("Enter the OTP sent to your registered number: "))
    return sent_otp == entered_otp

def create_or_login():
    name = input("Enter Name: ")

    if os.path.exists("user_data.json"):
        with open("user_data.json", "r") as file:
            user_data = json.load(file)
        if name in user_data:
            print(f"Welcome back, {name}!")
            return name, user_data[name]["Balance"], user_data[name]["PIN"]
        else:
            print(f"User {name} not found. Proceeding with account creation.")
    else:
        print("No users found. Proceeding with account creation.")

    initial_balance = float(input("Enter Your Balance: "))
    while initial_balance <= 0:
        print("Balance should be greater than 0.")
        initial_balance = float(input("Enter Your Balance: "))

    pin = input("Set Your PIN (4-digit): ")
    while len(pin) != 4 or not pin.isdigit():
        print("Invalid PIN. Enter a 4-digit numeric PIN.")
        pin = input("Set Your PIN (4-digit): ")

    otp = generate_otp()
    print(f"OTP for account creation is: {otp}")

    if not validate_otp(otp):
        print("OTP verification failed. Account creation aborted.")
        exit()

    return name, initial_balance, pin


name, initial_balance, pin = create_or_login()
atm = ATM(name, initial_balance, pin)

if name not in os.listdir():
    atm.save_account_details()

while True:
    entered_pin = input("Enter Your PIN: ")
    if atm.validate_pin(entered_pin):
        print(f"Welcome {atm.name}!")
        while True:
            print("\nOptions:")
            print("1. Deposit")
            print("2. Withdraw")
            print("3. View Transaction History")
            print("4. Exit")
            choice = input("Enter your choice: ")

            if choice == "1":
                deposit_amount = float(input("Enter the amount to deposit: "))
                atm.deposit(deposit_amount)
                print(f"Your current balance is: {atm.get_account_balance()}")

            elif choice == "2":
                withdrawal_amount = float(input("Enter the amount to withdraw: "))
                atm.withdraw(withdrawal_amount)
                print(f"Your current balance is: {atm.get_account_balance()}")

            elif choice == "3":
                transactions = atm.get_transaction_history()
                if transactions:
                    print("\nTransaction History:")
                    for index, transaction in enumerate(transactions, start=1):
                        print(f"{index}. {transaction['Type']} - Amount: {transaction['Amount']} - Balance: {transaction['Balance']}")
                else:
                    print("No transactions available.")

            elif choice == "4":
                print("Goodbye!")
                break
            else:
                print("Invalid choice. Please try again.")
        break
    else:
        print("Incorrect PIN. Please try again.")
```

---
