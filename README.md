from tkinter import *
import math

def leftClickButton(event):
    result = (float(textBoxWeight.get())/math.pow(float(textBoxHight.get())/100,2))
    if result<18:
        labelResult.configure(text = "น้ำหนักน้อย / ผอม")
    elif result>18.50 or result<22.90:
        labelResult.configure(text = "ปกติ (สุขภาพดี)")
    elif result>23 or result<24.90:
        labelResult.configure(text = "ท้วม / โรคอ้วนระดับ 1")
    elif result>25 or result<29.90:
        labelResult.configure(text = "อ้วน / โรคอ้วนระดับ 2")
    elif result>30:
        labelResult.configure(text = "อ้วนมาก / โรคอ้วนระดับ 3")

    ##print(float(textBoxWeight.get())/math.pow(float(textBoxHight.get())/100,2))
    ##labelResult.configure(text = float(textBoxWeight.get())/math.pow(float(textBoxHight.get())/100,2))

MainWindow = Tk()
labelHight = Label(MainWindow,text = "ส่วนสูง (Cm.)").grid(row = 0,column = 0)
textBoxHight = Entry(MainWindow)
textBoxHight.grid(row = 0,column = 1)
labelWeight = Label(MainWindow,text = "น้ำหนัก (Kg.)").grid(row = 1,column = 0)
textBoxWeight = Entry(MainWindow)
textBoxWeight.grid(row = 1,column = 1)
calculateButton = Button(MainWindow,text = "คำนวน BMI")
calculateButton.grid(row = 2)
calculateButton.bind('<Button-1>',leftClickButton)
labelResult = Label(MainWindow,text = "ผลลัพธ์")
labelResult.grid(row = 2,column = 1)
MainWindow.mainloop()
