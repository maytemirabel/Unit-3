# Quiz 35
## Code
Create a python class for a Bank Office that follows the UML diagram on the slides and passes the test file **test_quiz35.py**
```.py
import random
class Account:
    def __init__(self):
        self.balance = 0
        self.holder_name = ""
        self.holder_email = ""
        number1 = random.randint(100, 999)
        number2 = random.randint(10000, 99999)
        number3 = random.randint(0, 9)
        self.number = [f"{number1} - {number2} - {number3}"]

    def get_account_no(self):
        return self.number[0]

    def set_holder_name(self, name):
        if not isinstance(name, str):
            raise ValueError("Name must be a string")
        self.holder_name = name
        message = f"Holder's name set to {self.holder_name}"
        return message

    def set_holder_email(self,email):
        self.holder_email = email
        message = f"Holder's email set to {self.holder_email}"
        return message

    def get_balance(self):
        return self.balance

    def deposit(self,amount:int):
        self.balance += amount
        message = f"New balance: {self.balance} USD"
        return message
```

## Evidence of code
<img width="945" alt="Screen Shot 2023-02-08 at 13 37 50" src="https://user-images.githubusercontent.com/105724334/217434971-e43790d6-56d7-4a5a-861a-47c0439c90f0.png">

##### Figure 1: Screenshot displaying the test outcome
