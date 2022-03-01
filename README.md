from tkinter import *
from tkinter import messagebox
import time
window=Tk()
window.geometry('600x400')
window.title('Calculator')
window.maxsize(318, 334)
password = Entry(width=20,justify=RIGHT,font=('Arial',14))
password.grid(column=0,row=0,columnspan=20,stick='we')
frame = Label(password,text = 'Error',fg='red',width=10,font=('Arial',17))  
def add_digit(digit):
    value = password.get() + str(digit)
    if value[0]=='0':
        value=value[1:]
    password.delete(0, END)
    password.insert(0, value)
    if digit == c:
        password.delete(0, END)
    add_rotate()

def add_rotate():
    if len(password.get()) == 10:             
        frame.grid()
        password.delete(0, END)

def one_ce():
    try:
        solution = eval(password.get())
        messagebox.showinfo('Готово!',f'Решение найдено: {solution}')
    except NameError:
        messagebox.showerror('Ошибка!','Что-то написано не правильно')
    except SyntaxError:
        messagebox.showwarning('Внимание!','Вы что-то пропустили')
    except ZeroDivisionError:
        messagebox.showwarning('Внимание!','Деление на ноль!')

button0 = Button(text='0',bd=5,width=7,height=3,fg='orange',bg='grey',font=('Arial',13),anchor='center',command=lambda: add_digit(0))
button0.grid(column=0,row=4)
button1 = Button(text='1',bd=5,width=7,height=3,fg='orange',bg='grey',font=('Arial',13),anchor='center',command=lambda: add_digit(1))
button1.grid(column=0,row=3)
button4= Button(text='4',bd=5,width=7,height=3,fg='orange',bg='grey',font=('Arial',13),anchor='center',command=lambda: add_digit(4))
button4.grid(column=0,row=2)
button7 = Button(text='7',bd=5,width=7,height=3,fg='orange',bg='grey',font=('Arial',13),anchor='center',command=lambda: add_digit(7))
button7.grid(column=0,row=1)
button2= Button(text='2',bd=5,width=7,height=3,fg='orange',bg='grey',font=('Arial',13),anchor='center',command=lambda: add_digit(2))
button2.grid(column=1,row=3)
button5 = Button(text='5',bd=5,width=7,height=3,fg='orange',bg='grey',font=('Arial',13),anchor='center',command=lambda: add_digit(5))
button5.grid(column=1,row=2)
button8 = Button(text='8',bd=5,width=7,height=3,fg='orange',bg='grey',font=('Arial',13),anchor='center',command=lambda: add_digit(8))
button8.grid(column=1,row=1)
ravno = Button(text='=',bd=5,width=7,height=3,fg='orange',bg='grey',font=('Arial',13),anchor='center',command=one_ce)
ravno.grid(column=1,row=4)
button3 = Button(text='3',bd=5,width=7,height=3,fg='orange',bg='grey',font=('Arial',13),anchor='center',command=lambda: add_digit(3))
button3.grid(column=2,row=3)
button6 = Button(text='6',bd=5,width=7,height=3,fg='orange',bg='grey',font=('Arial',13),anchor='center',command=lambda: add_digit(6))
button6.grid(column=2,row=2)
button9 = Button(text='9',bd=5,width=7,height=3,fg='orange',bg='grey',font=('Arial',13),anchor='center',command=lambda: add_digit(9))
button9.grid(column=2,row=1)
c = Button(text='C',bd=5,width=7,height=3,fg='orange',bg='grey',font=('Arial',13),anchor='center',command=lambda: add_digit(c))
c.grid(column=2,row=4)
plus = Button(text='+',bd=5,width=7,height=3,fg='orange',bg='grey',font=('Arial',13),anchor='center',command=lambda: add_digit('+'))
plus.grid(column=3,row=1)
minuse = Button(text='-',bd=5,width=7,height=3,fg='orange',bg='grey',font=('Arial',13),anchor='center',command=lambda: add_digit('-'))
minuse.grid(column=3,row=2)
podelit = Button(text='/',bd=5,width=7,height=3,fg='orange',bg='grey',font=('Arial',13),anchor='center',command=lambda: add_digit('/'))
podelit.grid(column=3,row=3)
umnozit = Button(text='*',bd=5,width=7,height=3,fg='orange',bg='grey',font=('Arial',13),anchor='center',command=lambda: add_digit('*'))
umnozit.grid(column=3,row=4)
