# Pyqt-widget-creation
First and foremost, import all necessary libraries.
from PyQt5.QtWidgets import (
    for example: QApplication, QWidget, QLabel, QLineEdit, QPushButton, QVBoxLayout, QHBoxLayout, QMessageBox, QGridLayout
)

Create a class that inherits from QWidget. This will be your main application window.
class App(QWidget):
    def __init__(self):
        super().__init__()
        self.setWindowTitle("window name")
        self.init_ui()

Now in def init_ui(self) you can start creating.

**1. Creating input fields**
We need to use QLineEdit to allow the user to type in information.
self.name_input = QLineEdit()

Labels will help describe what each input field is for.
QLabel("name")

**2. Creating buttons**
First let's create a button using QPushButton.
btn_name = QPushButton("functionality")

Next, you can add functionality to the button. To do this we use clicked.connect.
btn_name.clicked.connect(self.function)

**3. Making grid**
Use QGridLayout to place widgets in a grid — rows and columns — to make your UI organized.
grid = QGridLayout()

let's try to put created fields in a row.
grid.addWidget(QLabel("name"), 0, 0)
grid.addWidget(self.name_input, 0, 1)
grid.addWidget(btn_name, 0, 2)

To do it in a column, try this.
grid.addWidget(QLabel("name"), 0, 0)
grid.addWidget(self.name_input, 1, 0)
grid.addWidget(btn_name, 2, 0) 

don't forget to tell you application to use grid.
self.setLayout(grid)
