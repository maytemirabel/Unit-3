# Quiz 42

## Python Code
```.py
from kivymd.app import MDApp
from kivymd.uix.screen import MDScreen


class MysteryA(MDScreen):
    def messageA(self):
        print("Printing from Mystery A")
        self.ids.label1.text = "This is mystery A. You pressed a button"

class MysteryB(MDScreen):
    pass

class quiz_42(MDApp):
    def build(self):
        return

test = quiz_42()
test.run()
```

## KivyMD
```
ScreenManager:
    id: screenmanager
    MysteryA:
        name: "MysteryA"
    MysteryB:
        name: "MysteryB"

<MysteryA>:
    name: "MysteryA"
    MDBoxLayout:
        orientation: "vertical"
        MDLabel:
            id: label1
            halign: "center"
        MDRaisedButton:
            text: "Click Here"
            on_press: app.root.current = "MysteryB"
            on_press: root.messageA()

<MysteryB>:
    name: "MysteryB"
    MDBoxLayout:
        orientation: "vertical"
        MDLabel:
            id: label2
            text: "This is Mystery B. You pressed a button"
            halign: "center"
        MDRaisedButton:
            text: "Click Here"
            on_press: app.root.current = "MysteryA"
```

## Evidence of code
<img width="788" alt="Screen Shot 2023-03-27 at 7 34 52" src="https://user-images.githubusercontent.com/105724334/227809058-2ba3cc98-5ba6-43ea-8a71-bea99a185bbd.png">

#### Figure 1: Screenshot displaying the test outcome
