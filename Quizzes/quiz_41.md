# Quiz 41
## Code
Write a program that creates the GUI of a Tic Tac Toe game
```.py
Screen:
    size: 500,500

    MDBoxLayout:
        orientation: "vertical"
        pos_hint: {"center_x": 0.5,"center_y":0.5}
        size_hint: .7, .8

        MDLabel:
            size_hint: 1, .1
            halign: "center"
            text: "Tic Tac Toe by Mayte"
            font_size: "60px"
            bold: True

        MDLabel:
            id: player
            size_hint: 1, .1
            halign: "center"
            text: "It is X's turn"
            font_size: "30px"

        MDBoxLayout:
            size_hint: 1,.8
            orientation: "vertical"
            spacing: 10
            MDBoxLayout:
                orientation: "horizontal"
                spacing: 20
                MDRectangleFlatButton:
                    id: button1
                    text: ""
                    text_color: "white"
                    md_bg_color: "#2a9d8f"
                    size_hint: .3,1
                   
                MDRectangleFlatButton:
                    id: button2
                    text: ""
                    text_color: "white"
                    md_bg_color: "#2a9d8f"
                    size_hint:.3,1

                MDRectangleFlatButton:
                    id: button3
                    text: ""
                    text_color: "white"
                    md_bg_color: "#2a9d8f"
                    size_hint:.3,1

            MDBoxLayout:
                orientation: "horizontal"
                spacing: 20
                MDRectangleFlatButton:
                    id: button4
                    text: ""
                    text_color: "white"
                    md_bg_color: "#2a9d8f"
                    size_hint: .3,1
                    
                MDRectangleFlatButton:
                    id: button5
                    text: ""
                    text_color: "white"
                    md_bg_color: "#2a9d8f"
                    size_hint:.3,1
                    on_release:
                        app.press(btn5)
                MDRectangleFlatButton:
                    id: button6
                    text: ""
                    text_color: "white"
                    md_bg_color: "#2a9d8f"
                    size_hint:.3,1

            MDBoxLayout:
                orientation: "horizontal"
                spacing: 20

                MDRectangleFlatButton:
                    id: button7
                    text: ""
                    text_color: "white"
                    md_bg_color: "#2a9d8f"
                    size_hint: .3, 1

                MDRectangleFlatButton:
                    id: button8
                    text: ""
                    text_color: "white"
                    md_bg_color: "#2a9d8f"
                    size_hint: .3, 1

                MDRectangleFlatButton:
                    id: button9
                    text: ""
                    text_color: "white"
                    md_bg_color: "#2a9d8f"
                    size_hint: .3, 1

```

## Evidence of code
<img width="790" alt="Screen Shot 2023-03-27 at 7 18 38" src="https://user-images.githubusercontent.com/105724334/227808168-6da2ca56-3648-43c2-a01d-3f30221462a3.png">

#### Figure 1: Screenshot displaying the test outcome
