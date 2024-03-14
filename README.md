from tkinter import *
import math


root = Tk()
root.title("Simple calculator")

root.configure(bg="#333333")

e = Entry(root, width= 35, borderwidth=5, bg= "White")

e.insert(0, "")
e.grid(row= 0, column= 0, columnspan= 3, padx= 10, pady= 10)

def button_click(Numbers):
     
     current = e.get()
     e.delete(0, END) 
     e.insert(0, str(current) + str(Numbers))
    
def button_add():
    global f_num
    global math
    math = "Addition"
    f_num = int(e.get())
    e.delete(0, END)

def button_subtract():
    global f_num
    global math
    math = "Subtraction"
    f_num = int(e.get())
    e.delete(0, END)
  
def button_multiply():
    global f_num
    global math
    math = "Multiplication"
    f_num = int(e.get())
    e.delete(0, END)


def button_divide():
    global f_num
    global math
    math = "Division"
    f_num = int(e.get())
    e.delete(0, END)

def button_clear():
    e.delete(0, END)

def button_equal():
    second_number = e.get()
    e.delete(0, END)
    if math == "Addition":
        e.insert(0, f_num + int(second_number))
    elif math == "Subtraction":
        e.insert(0, f_num - int(second_number))
    elif math == "Multiplication":
        e.insert(0, f_num * int(second_number))
    
    if math == "Division":
       if int(second_number) != 0:
          e.insert(0, f_num / int(second_number))
       else:
         e.insert(0, "Undifined")

    if math == "Power":
       e.insert(0, f_num** int(second_number))

    elif math == "Root":
       e.insert(0, f_num** (1/float(second_number)))

def button_power():
    global f_num
    global math
    math = "Power"
    f_num = int(e.get())
    e.delete(0, END)

def button_root():
    global f_num
    global math
    math = "Root"
    f_num = int(e.get())
    e.delete(0, END)

button_1 = Button(root, text="1", bg= "Orange" ,command= lambda: button_click(1))
button_2 = Button(root, text="2", bg= "Orange" ,command= lambda: button_click(2))
button_3 = Button(root, text="3", bg= "Orange" ,command= lambda: button_click(3))
button_4 = Button(root, text="4", bg= "Orange" ,command= lambda: button_click(4))
button_5 = Button(root, text="5", bg= "Orange" ,command= lambda: button_click(5))
button_6 = Button(root, text="6", bg= "Orange" ,command= lambda: button_click(6))
button_7 = Button(root, text="7", bg= "Orange" ,command= lambda: button_click(7))
button_8 = Button(root, text="8", bg= "Orange" ,command= lambda: button_click(8))
button_9 = Button(root, text="9", bg= "Orange" ,command= lambda: button_click(9))
button_0 = Button(root, text="0", bg= "Orange" ,command= lambda: button_click(0))
button_a = Button(root, text= "+", bg= "Orange" ,command= button_add)
button_s = Button(root, text= "-", bg= "Orange" ,command= button_subtract)
button_m = Button(root, text= "*", bg= "Orange" ,command= button_multiply)
button_d = Button(root, text= "/", bg= "Orange" ,command= button_divide)
button_p = Button(root, text= "^", bg="Orange", command= button_power)
button_r = Button(root, text="√", bg= "Orange", command= button_root)
button_clea = Button(root, text= "Clear", bg= "Orange" ,command= button_clear)
button_equa = Button(root, text= "Equal", bg= "Orange" ,command= button_equal)



button_1.grid(row= 3, column= 0)
button_2.grid(row= 3, column= 1)
button_3.grid(row= 3, column= 2)

button_4.grid(row= 2, column= 0)
button_5.grid(row= 2, column= 1)
button_6.grid(row= 2, column= 2)

button_7.grid(row= 1 , column= 0)
button_8.grid(row= 1, column=  1)
button_9.grid(row= 1, column=  2)

button_0.grid(row= 4, column= 0)
button_a.grid(row= 4, column= 1)
button_s.grid(row= 4, column= 2)

button_m.grid(row= 5, column= 0)
button_d.grid(row= 5, column= 1)
button_clea.grid(row= 5, column= 2)

button_equa.grid(row= 1, column= 3)
button_p.grid(row= 2, column= 3)
button_r.grid(row= 3, column= 3)


root.mainloop()
