# Quiz 33
## Code
Write the function **mystery** and pass the tests contained in the file **test_quiz_33.py**

```.py
def mystery(list1, list2):
    output = []
    for i in range(len(list1)):
        for n in range(len(list2)):
            if list1[i] == list2[n]:
                output.append(list1[i])
    return output
```

## Evidence of code
<img width="1367" alt="Screen Shot 2023-01-10 at 13 53 17" src="https://user-images.githubusercontent.com/105724334/211465158-b83754de-a1c7-4871-81c9-733b11e3a5fa.png">

#### Figure 1: Screenshot displaying the test outcome
