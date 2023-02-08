# Quiz 34
## Code
Create a new Python function called **to_roman(num)** that takes a single integer as input. It returns a string representing the Roman numeral equivalent of the input number. 

```.py
def to_roman(num:int):
    if num > 100:
        raise ValueError("Input must me less than or equal to 100")
    out = ""
    if num == 100:
        out = "C"
        num = 0
    if num >= 90:
        out += "XC"
        num -= 90
    if num >= 50:
        out += "L"
        num -= 50
    if num >= 40:
        out += "XL"
        num -= 40
    if num >= 10:
        out += "X" * (num // 10)
        num %= 10
    if num >= 9:
        out += "IX"
        num -= 9
    if num >= 5:
        out += "V"
        num -= 5
    if num >= 4:
        out += "IV"
        num -= 4
    if num >= 1:
        out += "I" * num
    return out
```

## Evidence of code
<img width="900" alt="Screen Shot 2023-02-09 at 0 18 07" src="https://user-images.githubusercontent.com/105724334/217571840-2c9a3e8f-5acc-4bd6-8904-63e16f676de9.png">

##### Figure 1: Screenshot displaying the test outcome
