# Quiz 39
Write a program that creates a GUI that adds +1 to a number

## Python Code
```.py
from kivymd.app import MDApp
class quiz_39(MDApp):
    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        self.count = 0
    def build(self):
        return
    def add(self):
        self.count += 1
        self.root.ids.counter.text = f"Count = {self.count}"

test = quiz_39()
test.run()

```

## Kivy Code
```
Screen:
    size: 500,500

    MDBoxLayout:
        orientation: "horizontal"
        alignment: "horizontal"
        pos_hint:{"center_x":.5, "center_y":.5}
        size_hint: .7,.3
        md_bg_color: "#8ecae6"

        MDLabel:
            halign: "center"
            valign: "center"
            id: counter
            text: "Count 0"
            size_hint:.5,1
            font_size: "34pt"
            md_bg_color: "#588157"

        MDRaisedButton:
            size_hint: .5, 1
            font_size: "34pt"
            text: "Add +1"
            on_release:
                app.add()
```

## Evidence of code
<img width="798" alt="Screen Shot 2023-02-08 at 14 06 41" src="https://user-images.githubusercontent.com/105724334/217439745-aa72d128-82ed-4f30-9430-42f3b20b9b4a.png">

#### Figure 1: Screenshot displaying the test outcome
