# Quiz 40
Write a program that changes the screen from light mode to dark mode. 
## Python Code
```.py
from kivymd.app import MDApp

class quiz_40(MDApp):
    def build(self):
        return

    def __init__(self, **kwargs):
        super().__init__(**kwargs)

    def change_mode(self):
        print(self.root.ids.main_screen.md_bg_color)
        if self.root.ids.main_screen.md_bg_color == [1.0, 1.0, 1.0, 1.0]:
            self.root.ids.main_screen.md_bg_color = "#000000"
            self.root.ids.change_button.text_color = 1, 1, 1, 1
            self.root.ids.name.text_color = 1, 1, 1, 1
            self.root.ids.change_button.text = "Light Mode"
        else:
            self.root.ids.main_screen.md_bg_color = "#FFFFFF"
            self.root.ids.change_button.text_color = 0, 0, 0, 1
            self.root.ids.name.text_color = 0, 0, 0, 1
            self.root.ids.change_button.text = "Dark Mode"

test = quiz_40()
test.run()

```

## Kivy Code
```
Screen:
    size:500,500
    MDBoxLayout:
        id: main_screen
        orientation:"vertical"
        md_bg_color: "#FFFFFF"

        MDLabel:
            id:name
            text: "Mayte"
            halign: "center"
            font_style: "H2"
            theme_text_color: "Custom"
            text_color: 0, 0, 0, 1
            pos_hint: {"center_x": .5, "center_y": .5}

        MDRaisedButton:
            id: change_button
            text: "Dark Mode"
            pos_hint: {"center_x": 0.06, "center_y": 0.1}
            on_release: app.change_mode()
```

## Evidence of code
<img width="795" alt="Screen Shot 2023-02-08 at 14 21 20" src="https://user-images.githubusercontent.com/105724334/217441575-0613a1e6-6d80-4fa3-b75a-acfea820fe77.png">

#### Figure 1: Screenshot displaying the outcome (light mode)

<img width="787" alt="Screen Shot 2023-02-08 at 14 21 33" src="https://user-images.githubusercontent.com/105724334/217441594-03d648a4-1fb8-4b14-8a83-f383a9a497c2.png">

#### Figure 2: Screenshot displaying the outcome (dark mode)

