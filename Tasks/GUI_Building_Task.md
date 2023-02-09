# GUI Building Task
Create a Currency Converter GUI that takes an integer representing an amount from your home country currency (MXN) and converts it into USD and JPY rounded to 2 decimals.

## Python Code
```.py
from kivymd.app import MDApp
class converter(MDApp):
    def __init__(self, **kwargs):
        super().__init__(**kwargs)
        self.original = 0
        self.output = 0
    def build(self):
        return

    def convert_currency(self, choice:str):
        if self.root.ids.user_input.text.isdigit():
            if 'USD' in choice:
                self.output = float("{:.2f}".format(int(self.root.ids.user_input.text) * 0.053))
            elif 'JPY' in choice:
                self.output = float("{:.2f}".format(int(self.root.ids.user_input.text) * 6.93))

            self.root.ids.final_label.text = f"{self.output} {choice}"
        else:
            self.root.ids.final_label.text = "Invalid Input!"
            self.root.ids.user_input.text = ""

test = converter()
test.run()
```

## Kivy
```
Screen:
    size: 500,500
    MDBoxLayout:
        id: main_box
        orientation: 'vertical'
        size_hint:1,.8
        pos_hint: {'center_x':0.5, 'center_y':0.5}

        MDLabel:
            text:"Currency Converter"
            halign: 'center'
            font_style: 'H3'
            bold: True
            size_hint: 1, .2
            pos_hint: {'center_x':0.5}

        MDTextField:
            id: user_input
            hint_text: "Enter amount in MXN"
            pos_hint: {'center_x':0.5, "center_y":0.6}
            size_hint: .7, .1

        MDBoxLayout:
            id: currency_box
            orientation: 'horizontal'
            size_hint: 1, .4
            pos_hint: {'center_x':0.5}

            MDLabel:
                id : hint_label
                text: "Click to convert -> "
                halign: 'center'
                size_hint: .3, 1
                pos_hint: {'center_x':0.5, 'center_y':0.6}

            MDBoxLayout:
                id: button_output_box
                orientation:"vertical"
                size_hint: .3, 1

                MDBoxLayout:
                    id: buttons_box
                    orientation: "horizontal"
                    size_hint: .7, 1
                    pos_hint: {'center_x':0.4, 'center_y':0.9}

                    MDChip:
                        text: "USD"
                        halign: 'center'
                        on_press: app.convert_currency("USD")
                        md_bg_color:"#002B41"
                        text_color: "#FFFFFF"

                    MDChip:
                        text: "JPY"
                        halign: 'center'
                        on_press: app.convert_currency("JPY")
                        md_bg_color:"#F20021"

                MDLabel:
                    id: final_label
                    halign: 'center'
                    font_style: 'H5'
                    bold: True
                    size_hint: .3, 1
                    font_size:40
```


## Evidence of code
<img width="800" alt="Screen Shot 2023-02-09 at 22 00 22" src="https://user-images.githubusercontent.com/105724334/217819908-552870a9-e6c4-4456-83fb-daf75ea7bee9.png">

#### Figure 1: Screenshot displaying the currency conversion (MXN to USD)
<img width="800" alt="Screen Shot 2023-02-09 at 22 00 35" src="https://user-images.githubusercontent.com/105724334/217819932-5338af3f-9e37-470f-8590-9355d785ebdd.png">

#### Figure 2: Screenshot displaying the currency conversion (MXN to JPY)

