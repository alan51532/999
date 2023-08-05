# 999
черновик 2 числа 
from tkinter import *
import tkinter as tk

import threading
import time
import sys

##import playsound
##from playsound import playsound

def muz():
        
        audiofile="C:\\na.wav"
        playsound(audiofile)
        
y = 0 ## пользватель 
x = 0
z = []
total = 0
def yap():
        root2 = tk.Tk()
        root2.title('Ahtung Ahtung Ahtung ')
        root2.geometry('630x250')
        root2.resizable(width=False, height=False)
              

        lab = tk.Label(root2, text=' Ладно, ладно...♥\n  вы наверно читер :) ', font=("Times New Roman", 22), foreground='Blue')
        lab.place(relx=0.10, rely=0.30)
        
        root2.mainloop()
        
def st():
        root.after(3000, root.destroy)
        root1 = tk.Tk()
        root1.title('Ahtung Ahtung Ahtung ')
        root1.geometry('630x250')
        root1.resizable(width=False, height=False)
              

        lab = tk.Label(root1, text=' Вы проиграли ♥\nЛюбое ваше число даст\n сумму больше или равную 50', font=("Times New Roman", 22), foreground='Blue')
        lab.place(relx=0.10, rely=0.30)
        
        root1.mainloop()
       



def ser(event):
        global y   ## пользоват 
        global x   ## ход пк
        global z   ## список
        global total## сумма 
        y = int(entry.get())
        if total == 0:
         if y<5:
          x = 5 - y
         if y>5:
          x = 16 - y
         if y == 5:
          x = 1

        if total in [5, 16, 27, 38, 49]:
          x = 11 - y
        if total >= 49:
          st()
        
          
         
         
        


        z.append(x+y)
        total = sum(z)
        print(z) 
    
        var=StringVar()
        var.set(x)
                   
         
        label8 = tk.Label(root, textvariable = var, font=("Helvetica", 15))
        label8.place(relx=0.54, rely=0.50)
         
        label4 = tk.Label(root, text='+', font=("Helvetica", 15))
        label4.place(relx=0.50, rely=0.50)

        var2=StringVar()
        var2.set(total)
         
        label3 = tk.Label(root, textvariable = var2, font=("Helvetica", 22))
        label3.place(relx=0.43, rely=0.76)
         
       
        label2 = tk.Label(root, text=' (ход  ПК ) ', font=("Helvetica", 15))
        label2.place(relx=0.60, rely=0.50)
         
        label1.destroy()
         
        label7 = tk.Label(root, text='Снова ваш ход ', font=("Helvetica", 12))
        label7.place(relx=0.1, rely=0.5)
         
        entry.delete(0, END)
        
      
        
          
##        if total >= 50:
##         sys.exit()      
       
                           

root = tk.Tk()
root.title('Сапер')
root.geometry('630x450')
root.resizable(width=False, height=False)
              

labe7 = tk.Label(text='Спонсор разработки сайт: Stoptut.ru ♥ ', font=("Times New Roman", 10),foreground='Blue')
labe7.pack(anchor="n")

label5 = tk.Label(root, text='    Цель игры: Называя по очереди числа от 1 до 10 и суммируя их\n сделать так, что бы  ваш ход  закончился на 49\n и какое бы число не назвал соперник\n    получится 50 и больше, что будет являться проигршем ☭', font=("Helvetica", 14))
label5.place(relx=0, rely=0.15)


label1 = tk.Label(root, text='Введите число первым ', font=("Helvetica", 12))
label1.place(relx=0.1, rely=0.5)

entry = tk.Entry(root, font="Arial", justify="center", width=4,)
entry.place(relx=0.4, rely=0.5)


label4 = tk.Label(root, text='Сумма чисел ', font=("Helvetica", 12))
label4.place(relx=0.37, rely=0.7)

label_summa = tk.Label(root, textvariable = '',  font=("Helvetica", 22))
label_summa.place(relx=0.45, rely=0.8)

##music_thread = threading.Thread(target=muz)
##music_thread.start()
entry.bind('<Return>', ser)







root.mainloop()
