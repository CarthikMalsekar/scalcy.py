# scalcy.py
smart calc
import tkinter
from tkinter import *

def add(a,b):
	return a+b

def sub(a,b):
	return a-b

def mul(a,b):
	return a*b

def	div(a,b):
	return a/b		

def mod(a,b):
	return a%b

def lcm(a,b):
	L=a if a>b else b
	while L<=a*b:
		if L%a==0 and L%b==0:
			return L
		L+=1

def hcf(a,b):
	H=a if a<b else b
	while H>=1:
		if a%H==0 and b%H==0:
			return H
		H-=1				

def extract_from_text(text):
	l=()
	for l in text.split(''):
		try:
			l.append(float(t))
		except ValueError:
			pass	
	return l		 

def calculate():
	text=textin.get()
	for word in text.split(''):
		if word.upper() in operations.keys():
			try:
				l= extract_from_text(text)
				r= operations(word.upper())(l(0)),(l(1))
				list.delete(0,END)
				list.insert(END,r)
  		    except:
  				list.delete(0,END)
  				list.insert(END,'something went wrong, enter again')
  			finally:
  				break
  		elif word.upper() not in operations.keys():





opertions('ADD':add, 'ADDITION':add, 'PLUS':add,
			'SUB':sub, 'MINUS':sub, 'SUBTRACTION':sub,
			)











win = tkinter.Tk()
win.geometry('500x300')
win.title('SCALCY')
win.configure(bg='orange')

l1 = Label(win,text='SUPER CALCULATOR',width=20,padx=10)
l1.place(x=150,y=10)

l2 = Label(win,text='Hi! I am Scalcy',width=14,padx=5)
l2.place(x=175,y=40)



l3 = Label(win,text='How can I help?',width=20,padx=3)
l3.place(x=156,y=140)

textin = StringVar()
e1 = Entry(win,width=45,textvariable=textin)
e1.place(x=100,y=170)


b1 = Button(win, text='PROCEED')
b1.place(x=200,y=200)


list = Listbox(win,width=30,height=3)
list.place(x=140,y=230)








win.mainloop()
