# Quiz 37
## Code
An Accounting firm needs a software package to calculate compound interest.
```.py
class CompoundInterest:
    def __init__(self, principal, rate, number_years):
        self.principal = principal
        self.rate = rate
        self.number_years = number_years

    def calculate_interest(self):
        interest = round(self.principal * (1+self.rate) ** self.number_years, 2)
        return interest

class AccountingProgram(CompoundInterest):
    def __init__(self):
        self.compound=CompoundInterest(0, 0, 0)

    def set_principal(self, principal):
        if principal < 0:
            raise ValueError("Principal should be greater than zero")
        else:
            self.compound.principal = principal

    def set_rate(self, rate:int):
        if rate < 0:
            raise ValueError("Interest rate should be greater than zero")
        else:
            self.compound.rate = rate

    def set_years(self, years:int):
        if years < 0:
            raise ValueError("Years should be greater than zero")
        else:
            self.compound.number_years = years

    def calculate_interest(self):
        return self.compound.calculate_interest()
```

## Evidence of code
<img width="1026" alt="Screen Shot 2023-02-09 at 0 33 27" src="https://user-images.githubusercontent.com/105724334/217575881-e5df36d2-af05-4782-9c25-9935d15c9e15.png">

##### Figure 1: Screenshot displaying the test outcome

## UML Diagram
![IMG_6F9E956E4D27-1](https://user-images.githubusercontent.com/105724334/217577465-b0c134e9-c0fc-4b54-a60a-d0eed81de347.jpeg)

##### Figure 2: The UML diagram for the code above
