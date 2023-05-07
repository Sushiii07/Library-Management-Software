# Before using this code install the module PyQt5
# Type "pip install PyQt5" in Command Prompt to download PyQt5

import sys
import mysql.connector
from PyQt5.QtCore import *
from PyQt5.QtGui import *
from PyQt5.QtWidgets import *

class MyWindow(QDialog):
    def __init__(self):
        super(MyWindow, self).__init__()
        self.Log()
        self.Register()
        self.setStyleSheet("QDialog"
                        "{"
                        "background-color: qlineargradient(x1:0, y1:1, x2:0, y2:0,"
                        "stop:0 rgb(0, 0, 0), stop:1 rgb(51, 51, 204));"
                        "}")

        self.label_1 = QLabel(self)
        self.label_1.setText("WELCOME TO")
        self.label_1.setStyleSheet("font: 25pt Microsoft YaHei UI;"
                                "font-weight : bold;"
                                "color : rgb(255, 255, 255);")
        self.label_1.move(500, 100)

        self.label_2 = QLabel(self)
        self.label_2.setText("FORTUNA")
        self.label_2.setStyleSheet("font: 25pt Microsoft YaHei UI;"
                                "font-weight : bold;"
                                "color : rgb(255, 0, 255);")
        self.label_2.move(550, 170)

    def Log(self):
        self.b1 = QPushButton(self)
        self.b1.setGeometry(525, 300, 300, 75)
        self.b1.setText("LOGIN")
        self.b1.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"
                        "QPushButton::hover"
                        "{"



                        "background-color: qlineargradient(x1:1, y1:0, x2:0, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "}")
        self.b1.clicked.connect(self.gotoLogin)

    def gotoLogin(self):
        widget.setCurrentIndex(widget.currentIndex()+1)
                         
    def Register(self):
        self.b1 = QPushButton(self)
        self.b1.setGeometry(525, 395, 300, 75)
        self.b1.setText("REGISTER")       
        self.b1.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"
                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:1, y1:0, x2:0, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "}")
        self.b1.clicked.connect(self.gotoReg)

    def gotoReg(self):
        widget.setCurrentIndex(widget.currentIndex()+2)

class Login(QDialog):
    def __init__(self):
        super(Login, self).__init__()
        self.setStyleSheet("QDialog"
                        "{"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(255, 153, 204), stop:1 rgb(255, 80, 80));"
                        "}"
                        )
        self.label = QLabel(self)
        self.label.setText("LOGIN")
        self.label.move(613, 100)
        self.label.setStyleSheet("font: 20pt Microsoft YaHei UI;"
                                "font-weight : bold;"
                                "color : rgb(100, 0, 100);")
        self.Back()
        self.txtbox()




    def txtbox(self):
        self.t1 = QLineEdit(self)
        self.t1.setPlaceholderText('  Username')
        self.t1.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                            "color : rgb(100, 100, 100);"
                            "border-radius: 21px;"
                            "background-color: rgba(255, 255, 255, 100)")
        self.t1.setGeometry(525, 220, 300, 60)
        self.t1.show()

        self.t2 = QLineEdit(self)
        self.t2.setPlaceholderText('  Password')
        self.t2.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                            "color : rgb(100, 100, 100);"
                            "border-radius: 21px;"
                            "background-color : rgba(255, 255, 255, 100);")
        self.t2.setEchoMode(QLineEdit.Password)
        self.t2.setGeometry(525, 300, 300, 60)
        self.t2.show()

        self.label_1 = QLabel(self)
        self.label_1.setGeometry(590, 480, 250, 50)
        self.label_1.setStyleSheet("font: 8pt Microsoft YaHei UI;"
                                "font-weight : bold;"
                                "color : rgb(255, 0, 0);")

        self.b1 = QPushButton(self)
        self.b1.setText("LOGIN")
        self.b1.setGeometry(525, 400, 300, 50)
        self.b1.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"
                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:1, y1:0, x2:0, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "}")
        self.b1.clicked.connect(self.login)

    def login(self):
        user_name = self.t1.text()
        passwd = self.t2.text()
        lst = (user_name,)



        mydb = mysql.connector.connect(host = "localhost", user = "root", passwd = "abc123")
        mycursor = mydb.cursor()
        mycursor.execute("USE library")
        mycursor.execute("SELECT Password FROM users WHERE Username = %s", lst)
        myrecords = mycursor.fetchone()
        if myrecords == None:
            self.label_1.setText("USER INFO DOESN'T EXIST")
        elif passwd == myrecords[0] and passwd != "":
            widget.setCurrentIndex(widget.currentIndex()+2)
        elif passwd == "":
            self.label_1.setText("ENTER ALL CREDENTIALS")
        elif passwd != mycursor.fetchone():
            self.label_1.setText("WRONG INFO")

        
    def Back(self):
        self.b1 = QPushButton(self)
        self.b1.setText("BACK")
        self.b1.setGeometry(210, 600, 100, 50)
        self.b1.setStyleSheet("QPushButton"
                            "{"
                            "font: 12pt Microsoft YaHei UI;"
                            "font-weight: bold;"
                            "color: rgb(255, 255, 255);"
                            "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                            "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                            "border-radius: 21px;"
                            "border-color: white;"
                            "border-style: solid;"
                            "border-width: 3px;"
                            "}"
                            "QPushButton::hover"
                            "{"
                            "background-color: qlineargradient(x1:1, y1:0, x2:0, y2:0,"
                            "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                            "}")
        self.b1.clicked.connect(self.Return)

    def Return(self):
        widget.setCurrentIndex(widget.currentIndex()-1)

class Register(QDialog):
    def __init__(self):
        super(Register, self).__init__()
        self.setStyleSheet("QDialog"
                        "{"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "}")
        self.label = QLabel(self)
        self.label.setText("Create an Account")



        self.label.move(493, 100)
        self.label.setStyleSheet("font: 20pt Microsoft YaHei UI;"
                                "font-weight : bold;"
                                "color : rgb(100, 0, 100);")
        self.txtbox()
        self.Back()

    def txtbox(self):
        self.t1 = QLineEdit(self)
        self.t1.setPlaceholderText('Admission No.')
        self.t1.setGeometry(525, 190, 300, 45)
        self.t1.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                            "color : rgb(100, 100, 100);"
                            "border-radius: 16px;"
                            "background-color: rgba(255, 255, 255, 180)")
        self.t1.show()

        self.t2 = QLineEdit(self)
        self.t2.setPlaceholderText('Name')
        self.t2.setGeometry(525, 250, 300, 45)
        self.t2.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                            "color : rgb(100, 100, 100);"
                            "border-radius: 16px;"
                            "background-color: rgba(255, 255, 255, 180)")
        self.t2.show()

        self.t3 = QLineEdit(self)
        self.t3.setPlaceholderText('Username')
        self.t3.setGeometry(525, 310, 300, 45)
        self.t3.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                            "color : rgb(100, 100, 100);"
                            "border-radius: 16px;"
                            "background-color: rgba(255, 255, 255, 180)")
        self.t3.show()

        self.t4 = QLineEdit(self)
        self.t4.setPlaceholderText('Class')
        self.t4.setGeometry(525, 370, 300, 45)
        self.t4.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                            "color : rgb(100, 100, 100);"
                            "border-radius: 16px;"
                            "background-color: rgba(255, 255, 255, 180)")
        self.t4.show()

        self.t5 = QLineEdit(self)
        self.t5.setPlaceholderText('Password')
        self.t5.setGeometry(525, 430, 300, 45)
        self.t5.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                            "color : rgb(100, 100, 100);"
                            "border-radius: 16px;"
                            "background-color: rgba(255, 255, 255, 180)")
        self.t5.show()



        self.label_1 = QLabel(self)
        self.label_1.setGeometry(590, 480, 250, 50)
        self.label_1.setStyleSheet("font: 8pt Microsoft YaHei UI;"
                                "font-weight : bold;"
                                "color : rgb(255, 0, 0);")

        self.b1 = QPushButton(self)
        self.b1.setText("Register")
        self.b1.setGeometry(575, 550, 200, 50)
        self.b1.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "border-radius: 19px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"
                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:1, y1:0, x2:0, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "}")
        self.b1.clicked.connect(self.Register_User)

    def Register_User(self):
        a = int(self.t1.text())
        b = self.t2.text()
        c = self.t3.text()
        d = self.t4.text()
        e = self.t5.text()
        lst = (a,b,c,d,e)
        mydb = mysql.connector.connect(host = "localhost", user = "root", passwd = "abc123")
        mycursor = mydb.cursor()
        mycursor.execute("USE library")
        mycursor.execute("INSERT INTO users VALUES (%s,%s,%s,%s,%s)", lst)
        mydb.commit()
        self.label_1.setText("ACCOUNT CREATED")

    def Back(self):
        self.b = QPushButton(self)
        self.b.setText("BACK")
        self.b.setGeometry(210, 600, 100, 50)
        self.b.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"



                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(186, 140, 99), stop:1 rgb(240, 53, 218));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"
                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:1, y1:0, x2:0, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "}")
        self.b.clicked.connect(self.back)

    def back(self):
        widget.setCurrentIndex(widget.currentIndex()-2)

class Functions(QDialog):
    def __init__(self):
        super(Functions, self).__init__()
        self.setGeometry(1080, 200, 720, 800)
        self.setStyleSheet("QDialog" 
                        "{"
                        "background-image:url(C:/Users/shash/Desktop/LMS/bookshelf.png);"
                        "}")
        self.label = QLabel(self)
        self.label.setText("")
        self.label.move(50, 50)
        self.Add()
        self.Remove()
        self.Issue()
        self.Return()
        self.Show_All()
        self.Show_One() 
        self.Back()
                           
    def Add(self):
        self.b1 = QPushButton(self)
        self.b1.setGeometry(180, 260, 300, 100)
        self.b1.setText("Add Book")
        self.b1.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgba(102, 0, 51, 150), stop:1 rgba(153, 0, 0, 150));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"



                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(204, 0, 102), stop:1 rgb(255, 102, 102));"
                        "}")
        self.b1.clicked.connect(self.add_book)

    def add_book(self):
        widget.setCurrentIndex(widget.currentIndex()+1)

    def Remove(self):
        self.b2 = QPushButton(self)
        self.b2.setGeometry(500, 260, 300, 100)
        self.b2.setText("Delete Book")
        self.b2.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgba(102, 0, 51, 150), stop:1 rgba(153, 0, 0, 150));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"
                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(204, 0, 102), stop:1 rgb(255, 102, 102));"
                        "}")
        self.b2.clicked.connect(self.del_book)

    def del_book(self):
        widget.setCurrentIndex(widget.currentIndex()+2)

    def Issue(self):
        self.b3 = QPushButton(self)
        self.b3.setGeometry(820, 260, 300, 100)
        self.b3.setText("Issue a book")
        self.b3.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgba(102, 0, 51, 150), stop:1 rgba(153, 0, 0, 150));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"



                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(204, 0, 102), stop:1 rgb(255, 102, 102));"
                        "}")
        self.b3.clicked.connect(self.issue_book)

    def issue_book(self):
        widget.setCurrentIndex(widget.currentIndex()+3)

    def Return(self):
        self.b4 = QPushButton(self)
        self.b4.setGeometry(180, 400, 300, 100)
        self.b4.setText("Return a book")
        self.b4.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgba(102, 0, 51, 150), stop:1 rgba(153, 0, 0, 150));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"
                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(204, 0, 102), stop:1 rgb(255, 102, 102));"
                        "}")
        self.b4.clicked.connect(self.return_book)

    def return_book(self):
        widget.setCurrentIndex(widget.currentIndex()+4)

    def Show_All(self):
        self.b5 = QPushButton(self)
        self.b5.setGeometry(500, 400, 300, 100)
        self.b5.setText("Show all records")
        self.b5.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgba(102, 0, 51, 150), stop:1 rgba(153, 0, 0, 150));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"



                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(204, 0, 102), stop:1 rgb(255, 102, 102));"
                        "}")
        self.b5.clicked.connect(self.show_all)

    def show_all(self):
         widget.setCurrentIndex(widget.currentIndex()+6)

    def Show_One(self):
        self.b6 = QPushButton(self)
        self.b6.setGeometry(820, 400, 300, 100)
        self.b6.setText("Show one record")
        self.b6.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgba(102, 0, 51, 150), stop:1 rgba(153, 0, 0, 150));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"
                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(204, 0, 102), stop:1 rgb(255, 102, 102));"
                        "}")
        self.b6.clicked.connect(self.show_one)

    def show_one(self):
         widget.setCurrentIndex(widget.currentIndex()+5)
        
    def Back(self):
        self.b = QPushButton(self)
        self.b.setText("BACK")
        self.b.setGeometry(210, 600, 100, 50)
        self.b.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(186, 140, 99), stop:1 rgb(240, 53, 218));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"



                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:1, y1:0, x2:0, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "}")
        self.b.clicked.connect(self.back)

    def back(self):
        widget.setCurrentIndex(widget.currentIndex()-2)

class Add_Book(QDialog):
    def __init__(self):
        super(Add_Book, self).__init__()
        self.setStyleSheet("QDialog" 
                        "{"
                        "border-image: url(C:/Users/shash/Desktop/LMS/1.jpeg);"
                        "}")
        self.label = QLabel(self)
        self.label.setText("Add a book")
        self.label.move(560, 100)
        self.label.setStyleSheet("font: 20pt Microsoft YaHei UI;"
                                "font-weight : bold;"
                                "color : rgb(255, 255, 255);")
        self.txtbox()
        self.Back()

    def txtbox(self):
        self.t1 = QLineEdit(self)
        self.t1.setGeometry(525, 230, 300, 50)
        self.t1.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                            "color : rgb(100, 100, 100);"
                            "border-radius: 15px;"
                            "background-color: rgba(255, 255, 255, 200)")
        self.t1.setPlaceholderText('  Book ID')
        self.t1.show()

        self.t2 = QLineEdit(self)
        self.t2.setGeometry(525, 310, 300, 50)
        self.t2.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                                "color : rgb(100, 100, 100);"
                                "border-radius: 15px;"
                                "background-color: rgba(255, 255, 255, 200)")
        self.t2.setPlaceholderText('  Book Name')
        self.t2.show()

        self.t3 = QLineEdit(self)
        self.t3.setGeometry(525, 390, 300, 50)
        self.t3.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                                "color : rgb(100, 100, 100);"
                                "border-radius: 15px;"
                                "background-color: rgba(255, 255, 255, 200)")
        self.t3.setPlaceholderText('  Author Name')



        self.t3.show()

        self.b1 = QPushButton(self)
        self.b1.setText("ADD")
        self.b1.setGeometry(500, 600, 100, 50)
        self.b1.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"
                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:1, y1:0, x2:0, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "}")
        self.b1.clicked.connect(self.Add)

    def Add(self):
        a = int(self.t1.text())
        b = self.t2.text()
        c = self.t3.text()
        lst = (a,b,c)
        widget.setCurrentIndex(widget.currentIndex()-1)
        mydb = mysql.connector.connect(host = "localhost", user = "root", passwd = "abc123")
        mycursor = mydb.cursor()
        mycursor.execute("USE library")
        mycursor.execute("INSERT INTO booklist (Book_ID, Book_Name, Author_Name)" 
                        "VALUES (%s,%s,%s)", lst)
        mydb.commit()

    def Back(self):
        self.b = QPushButton(self)
        self.b.setText("BACK")
        self.b.setGeometry(210, 600, 100, 50)
        self.b.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(186, 140, 99), stop:1 rgb(240, 53, 218));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"



                        "border-width: 3px;"
                        "}"
                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:1, y1:0, x2:0, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "}")
        self.b.clicked.connect(self.back)

    def back(self):
        widget.setCurrentIndex(widget.currentIndex()-1)

class Delete_Book(QDialog):
    def __init__(self):
        super(Delete_Book, self).__init__()
        self.setStyleSheet("QDialog" 
                        "{"
                        "border-image: url(C:/Users/shash/Desktop/LMS/8.jpg);"
                        "}")
        self.label = QLabel(self)
        self.label.setText("Delete a book")
        self.label.move(560, 100)
        self.label.setStyleSheet("font: 20pt Microsoft YaHei UI;"
                                "font-weight : bold;"
                                "color : rgb(255, 255, 255);")
        self.txtbox()
        self.Back()

    def txtbox(self):
        self.t1 = QLineEdit(self)
        self.t1.setGeometry(525, 230, 300, 50)
        self.t1.setPlaceholderText('Book ID')
        self.t1.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                            "color : rgb(100, 100, 100);"
                            "border-radius: 15px;"
                            "background-color: rgba(255, 255, 255, 200)")
        self.t1.show()

        self.t2 = QLineEdit(self)
        self.t2.setGeometry(525, 310, 300, 50)
        self.t2.setPlaceholderText('Book name')
        self.t2.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                            "color : rgb(100, 100, 100);"
                            "border-radius: 15px;"
                            "background-color: rgba(255, 255, 255, 200)")
        self.t2.show()

        self.b1 = QPushButton(self)
        self.b1.setText("DELETE")
        self.b1.setGeometry(500, 600, 100, 50)
        self.b1.setStyleSheet("QPushButton"
                        "{"



                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(186, 140, 99), stop:1 rgb(240, 53, 218));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"
                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:1, y1:0, x2:0, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "}")
        self.b1.clicked.connect(self.Del)

    def Del(self):
        a = self.t1.text()
        b = self.t2.text()
        lst = (a, b)
        widget.setCurrentIndex(widget.currentIndex()-2)
        mydb = mysql.connector.connect(host = "localhost", user = "root", passwd = "abc123")
        mycursor = mydb.cursor()
        mycursor.execute("USE library")
        mycursor.execute("DELETE FROM booklist WHERE Book_ID = %s AND Book_Name = %s", lst)
        mydb.commit()

    def Back(self):
        self.b = QPushButton(self)
        self.b.setText("BACK")
        self.b.setGeometry(210, 600, 100, 50)
        self.b.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(186, 140, 99), stop:1 rgb(240, 53, 218));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"
                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:1, y1:0, x2:0, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "}")



        self.b.clicked.connect(self.back)

    def back(self):
        widget.setCurrentIndex(widget.currentIndex()-2)

class Issue_Book(QDialog):
    def __init__(self):
        super(Issue_Book, self).__init__()
        self.setStyleSheet("QDialog" 
                        "{"
                        "border-image: url(C:/Users/shash/Desktop/LMS/3.jpg);"
                        "}")
        self.label = QLabel(self)
        self.label.setText("Issue a book")
        self.label.move(560, 100)
        self.label.setStyleSheet("font: 20pt Microsoft YaHei UI;"
                                "font-weight : bold;"
                                "color : rgb(255, 255, 255);")
        self.txtbox()
        self.Back()

    def txtbox(self):
        self.t1 = QLineEdit(self)
        self.t1.setGeometry(525, 230, 300, 50)
        self.t1.setPlaceholderText('Book ID')
        self.t1.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                            "color : rgb(100, 100, 100);"
                            "border-radius: 15px;"
                            "background-color: rgba(255, 255, 255, 200)")
        self.t1.show()

        self.t2 = QLineEdit(self)
        self.t2.setGeometry(525, 310, 300, 50)
        self.t2.setPlaceholderText('Book Name')
        self.t2.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                            "color : rgb(100, 100, 100);"
                            "border-radius: 15px;"
                            "background-color: rgba(255, 255, 255, 200)")
        self.t2.show()

        self.t3 = QLineEdit(self)
        self.t3.setGeometry(525, 390, 300, 50)
        self.t3.setPlaceholderText('Issued By')
        self.t3.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                            "color : rgb(100, 100, 100);"
                            "border-radius: 15px;"
                            "background-color: rgba(255, 255, 255, 200)")
        self.t3.show()

        self.b1 = QPushButton(self)
        self.b1.setText("Issue")
        self.b1.setGeometry(500, 600, 100, 50)



        self.b1.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(186, 140, 99), stop:1 rgb(240, 53, 218));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"
                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:1, y1:0, x2:0, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "}")
        self.b1.clicked.connect(self.Issue)

    def Issue(self):
        a = self.t1.text()
        b = self.t2.text()
        c = self.t3.text()
        lst = (c,a,b)
        widget.setCurrentIndex(widget.currentIndex()-3)
        mydb = mysql.connector.connect(host = "localhost", user = "root", passwd = "abc123")
        mycursor = mydb.cursor()
        mycursor.execute("USE library")
        mycursor.execute("UPDATE booklist SET Borrowed_By = %s" 
                        "WHERE Book_ID = %s AND Book_Name = %s", lst)
        mydb.commit()
        print(a, b)

    def Back(self):
        self.b = QPushButton(self)
        self.b.setText("BACK")
        self.b.setGeometry(210, 600, 100, 50)
        self.b.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(186, 140, 99), stop:1 rgb(240, 53, 218));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"
                        "QPushButton::hover"
                        "{"



                        "background-color: qlineargradient(x1:1, y1:0, x2:0, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "}")
        self.b.clicked.connect(self.back)

    def back(self):
        widget.setCurrentIndex(widget.currentIndex()-3)

class Return_Book(QDialog):
    def __init__(self):
        super(Return_Book, self).__init__()
        self.setStyleSheet("QDialog" 
                        "{"
                        "border-image: url(C:/Users/shash/Desktop/LMS/8.png);"
                        "}")
        self.label = QLabel(self)
        self.label.setText("Return a book")
        self.label.move(560, 100)
        self.label.setStyleSheet("font: 20pt Microsoft YaHei UI;"
                                "font-weight : bold;"
                                "color : rgb(255, 255, 255);")
        self.txtbox()
        self.Back()

    def txtbox(self):
        self.t1 = QLineEdit(self)
        self.t1.setGeometry(525, 230, 300, 50)
        self.t1.setPlaceholderText('Book ID')
        self.t1.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                            "color : rgb(100, 100, 100);"
                            "border-radius: 15px;"
                            "background-color: rgba(255, 255, 255, 200)")
        self.t1.show()

        self.t2 = QLineEdit(self)
        self.t2.setGeometry(525, 310, 300, 50)
        self.t2.setPlaceholderText('Book Name')
        self.t2.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                            "color : rgb(100, 100, 100);"
                            "border-radius: 15px;"
                            "background-color: rgba(255, 255, 255, 200)")
        self.t2.show()

        self.b1 = QPushButton(self)
        self.b1.setText("Return")
        self.b1.setGeometry(500, 600, 100, 50)
        self.b1.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"



                        "stop:0 rgb(186, 140, 99), stop:1 rgb(240, 53, 218));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"
                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:1, y1:0, x2:0, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "}")
        self.b1.clicked.connect(self.Return)

    def Return(self):
        a = self.t1.text()
        b = self.t2.text()
        lst = (a,b)
        widget.setCurrentIndex(widget.currentIndex()-4)
        mydb = mysql.connector.connect(host = "localhost", user = "root", passwd = "abc123")
        mycursor = mydb.cursor()
        mycursor.execute("USE library")
        mycursor.execute("UPDATE booklist SET Borrowed_By = 'AVAILABLE'" 
                        "WHERE Book_ID = %s AND Book_Name = %s", lst)
        mydb.commit()
        print(a, b)

    def Back(self):
        self.b = QPushButton(self)
        self.b.setText("BACK")
        self.b.setGeometry(210, 600, 100, 50)
        self.b.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(186, 140, 99), stop:1 rgb(240, 53, 218));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"
                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:1, y1:0, x2:0, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "}")
        self.b.clicked.connect(self.back)

    def back(self):
        widget.setCurrentIndex(widget.currentIndex()-4)



class Show_One_Rec(QDialog):
    def __init__(self):
        super(Show_One_Rec, self).__init__()
        self.setStyleSheet("QDialog" 
                        "{"
                        "border-image: url(C:/Users/shash/Desktop/LMS/5.jpeg);"
                        "}")
        self.label = QLabel(self)
        self.label.setText("Show one record")
        self.label.move(560, 100)
        self.label.setStyleSheet("font: 20pt Microsoft YaHei UI;"
                                "font-weight : bold;"
                                "color : rgb(255, 255, 255);")
        self.txtbox()
        self.Back()
 
    def txtbox(self):
        self.t1 = QLineEdit(self)
        self.t1.setGeometry(200, 230, 300, 50)
        self.t1.setPlaceholderText("Book ID")
        self.t1.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                            "color : rgb(100, 100, 100);"
                            "border-radius: 15px;"
                            "background-color: rgba(255, 255, 255, 200)")
        self.t1.show()

        self.t2 = QLineEdit(self)
        self.t2.setGeometry(200, 310, 300, 50)
        self.t2.setPlaceholderText("Book Name")
        self.t2.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                            "color : rgb(100, 100, 100);"
                            "border-radius: 15px;"
                            "background-color: rgba(255, 255, 255, 200)")
        self.t2.show()

        self.label_1 = QLabel(self)
        self.label_1.setGeometry(750, 200, 300, 40)
        self.label_1.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                                "font-weight : bold;"
                                "background-color: rgba(255, 255, 255, 200);"
                                "border-color: #ffffff;"
                                "border-style: solid;"
                                "border-width: 3px;"
                                "color : rgb(0, 0, 0);")

        self.label_2 = QLabel(self)
        self.label_2.setGeometry(750, 260, 300, 40)
        self.label_2.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                                "font-weight : bold;"
                                "background-color: rgba(255, 255, 255, 200);"
                                "border-color: #ffffff;"
                                "border-style: solid;"



                                "border-width: 3px;"
                                "color : rgb(0, 0, 0);")

        self.label_3 = QLabel(self)
        self.label_3.setGeometry(750, 320, 300, 40)
        self.label_3.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                                "font-weight : bold;"
                                "background-color: rgba(255, 255, 255, 200);"
                                "border-color: #ffffff;"
                                "border-style: solid;"
                                "border-width: 3px;"
                                "color : rgb(0, 0, 0);")

        self.label_4 = QLabel(self)
        self.label_4.setGeometry(750, 380, 300, 40)
        self.label_4.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                                "font-weight : bold;"
                                "background-color: rgba(255, 255, 255, 200);"
                                "border-color: #ffffff;"
                                "border-style: solid;"
                                "border-width: 3px;"
                                "color : rgb(0, 0, 0);")

        self.label_5 = QLabel(self)
        self.label_5.setGeometry(750, 440, 300, 40)
        self.label_5.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                                "font-weight : bold;"
                                "background-color: rgba(255, 255, 255, 200);"
                                "border-color: #ffffff;"
                                "border-style: solid;"
                                "border-width: 3px;"
                                "color : rgb(0, 0, 0);")

        self.label_6 = QLabel(self)
        self.label_6.setGeometry(750, 500, 300, 40)
        self.label_6.setStyleSheet("font: 10pt Microsoft YaHei UI;"
                                "font-weight : bold;"
                                "background-color: rgba(255, 255, 255, 200);"
                                "border-color: #ffffff;"
                                "border-style: solid;"
                                "border-width: 3px;"
                                "color : rgb(0, 0, 0);")

        self.b1 = QPushButton(self)
        self.b1.setText("show")
        self.b1.setGeometry(500, 600, 100, 50)
        self.b1.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"



                        "stop:0 rgb(186, 140, 99), stop:1 rgb(240, 53, 218));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"
                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:1, y1:0, x2:0, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "}")
        self.b1.clicked.connect(self.showone)
    
    def showone(self):
        a = self.t1.text()
        b = self.t2.text()
        lst = (a, b)
        mydb = mysql.connector.connect(host = "localhost", user = "root", passwd = "abc123")
        mycursor = mydb.cursor()
        mycursor.execute("USE library")
        mycursor.execute("SELECT * FROM booklist WHERE Book_ID = %s OR Book_Name = %s", lst)
        myrecords = mycursor.fetchone()
        a1 = myrecords[0]
        a2 = myrecords[1]
        a3 = myrecords[2]
        a4 = myrecords[3]
        a5 = myrecords[4]
        a6 = myrecords[5]
        self.label_1.setText(str(a1))
        self.label_2.setText(str(a2))
        self.label_3.setText(str(a3))
        self.label_4.setText(str(a4))
        self.label_5.setText(str(a5))
        self.label_6.setText(str(a6))

    def Back(self):
        self.b = QPushButton(self)
        self.b.setText("BACK")
        self.b.setGeometry(210, 600, 100, 50)
        self.b.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(186, 140, 99), stop:1 rgb(240, 53, 218));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"



                        "}"
                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:1, y1:0, x2:0, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "}")
        self.b.clicked.connect(self.back)

    def back(self):
        widget.setCurrentIndex(widget.currentIndex()-5)

class Show_All_Rec(QDialog):
    def __init__(self):
        super(Show_All_Rec, self).__init__()
        self.setStyleSheet("QDialog"
                        "{"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "}")
        self.Create_Table()
        self.layout = QVBoxLayout()
        self.layout.addWidget(self.tableWidget)
        self.setLayout(self.layout)
        self.Back()

    def Create_Table(self):
        self.tableWidget = QTableWidget()
        self.tableWidget.horizontalHeader().setSectionResizeMode(QHeaderView.Stretch)

        mydb = mysql.connector.connect(host = "localhost", user = "root", passwd = "abc123")
        mycursor = mydb.cursor()
        mycursor.execute("USE library")
        mycursor.execute("SELECT * FROM booklist")
        myrecords = mycursor.fetchall()

        self.tableWidget.setRowCount(len(myrecords)+1)
        self.tableWidget.setColumnCount(6)
        for x in myrecords:
            for i in range(0,6):
                self.tableWidget.setItem(myrecords.index(x)+1, i, QTableWidgetItem(str(x[i])))

        self.tableWidget.setItem(0,0, QTableWidgetItem("Book ID"))
        self.tableWidget.setItem(0,1, QTableWidgetItem("Book Name"))
        self.tableWidget.setItem(0,2, QTableWidgetItem("Author Name"))
        self.tableWidget.setItem(0,3, QTableWidgetItem("Issued By"))
        self.tableWidget.setItem(0,4, QTableWidgetItem("Due Date"))
        self.tableWidget.setItem(0,5, QTableWidgetItem("Status"))
        
    def Back(self):
        self.b = QPushButton(self)



        self.b.setText("BACK")
        self.b.setGeometry(210, 600, 100, 50)
        self.b.setStyleSheet("QPushButton"
                        "{"
                        "font: 12pt Microsoft YaHei UI;"
                        "font-weight: bold;"
                        "color: rgb(255, 255, 255);"
                        "background-color: qlineargradient(x1:0, y1:0, x2:1, y2:0,"
                        "stop:0 rgb(186, 140, 99), stop:1 rgb(240, 53, 218));"
                        "border-radius: 21px;"
                        "border-color: white;"
                        "border-style: solid;"
                        "border-width: 3px;"
                        "}"
                        "QPushButton::hover"
                        "{"
                        "background-color: qlineargradient(x1:1, y1:0, x2:0, y2:0,"
                        "stop:0 rgb(61, 217, 245), stop:1 rgb(240, 53, 218));"
                        "}")
        self.b.clicked.connect(self.back)

    def back(self):
        widget.setCurrentIndex(widget.currentIndex()-6)

app = QApplication(sys.argv)
widget = QStackedWidget()
widget.addWidget(MyWindow())            #1
widget.addWidget(Login())               #2
widget.addWidget(Register())            #3
widget.addWidget(Functions())           #4
widget.addWidget(Add_Book())            #5
widget.addWidget(Delete_Book())         #6
widget.addWidget(Issue_Book())          #7
widget.addWidget(Return_Book())         #8
widget.addWidget(Show_One_Rec())        #9
widget.addWidget(Show_All_Rec())        #10
widget.setFixedHeight(750)
widget.setFixedWidth(1350)
app.setWindowIcon(QIcon('C:\\Users\\shash\\Desktop\\LMS\\bookshelf 128.png'))
widget.setWindowTitle("Library Dash")
widget.show()

try:
    sys.exit(app.exec_())
except:
    print("Exiting")
