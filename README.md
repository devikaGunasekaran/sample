# CODESOFT
import tkinter as tk

# Function to update expression in the text entry box
def press(num):
    global expression
    expression = expression + str(num)
    equation.set(expression)

# Function to evaluate the final expression
def equalpress():
    try:
        global expression
        total = str(eval(expression))
        equation.set(total)
        expression = ""
    except:
        equation.set("error")
        expression = ""

# Function to clear the text entry box
def clear():
    global expression
    expression = ""
    equation.set("")

# Main program
if __name__ == "__main__":
    expression = ""
    
    # Create the GUI window
    gui = tk.Tk()
    gui.configure(background="light blue")
    gui.title("Simple Calculator")
    gui.geometry("300x400")
    
    equation = tk.StringVar()
    
    # Create the text entry box for displaying the expression
    expression_field = tk.Entry(gui, textvariable=equation, font=('Arial', 18))
    expression_field.grid(columnspan=4, ipadx=8, ipady=10)
    
    # Button parameters
    btn_params = {'fg': 'black', 'bg': 'white', 'height': 3, 'width': 7, 'font': ('Arial', 14)}

    # Create buttons
    button1 = tk.Button(gui, text=' 1 ', command=lambda: press(1), **btn_params)
    button1.grid(row=2, column=0)
    
    button2 = tk.Button(gui, text=' 2 ', command=lambda: press(2), **btn_params)
    button2.grid(row=2, column=1)
    
    button3 = tk.Button(gui, text=' 3 ', command=lambda: press(3), **btn_params)
    button3.grid(row=2, column=2)
    
    button4 = tk.Button(gui, text=' 4 ', command=lambda: press(4), **btn_params)
    button4.grid(row=3, column=0)
    
    button5 = tk.Button(gui, text=' 5 ', command=lambda: press(5), **btn_params)
    button5.grid(row=3, column=1)
    
    button6 = tk.Button(gui, text=' 6 ', command=lambda: press(6), **btn_params)
    button6.grid(row=3, column=2)
    
    button7 = tk.Button(gui, text=' 7 ', command=lambda: press(7), **btn_params)
    button7.grid(row=4, column=0)
    
    button8 = tk.Button(gui, text=' 8 ', command=lambda: press(8), **btn_params)
    button8.grid(row=4, column=1)
    
    button9 = tk.Button(gui, text=' 9 ', command=lambda: press(9), **btn_params)
    button9.grid(row=4, column=2)
    
    button0 = tk.Button(gui, text=' 0 ', command=lambda: press(0), **btn_params)
    button0.grid(row=5, column=1)
    
    plus = tk.Button(gui, text=' + ', command=lambda: press("+"), **btn_params)
    plus.grid(row=2, column=3)
    
    minus = tk.Button(gui, text=' - ', command=lambda: press("-"), **btn_params)
    minus.grid(row=3, column=3)
    
    multiply = tk.Button(gui, text=' * ', command=lambda: press("*"), **btn_params)
    multiply.grid(row=4, column=3)
    
    divide = tk.Button(gui, text=' / ', command=lambda: press("/"), **btn_params)
    divide.grid(row=5, column=3)
    
    equal = tk.Button(gui, text=' = ', command=equalpress, **btn_params)
    equal.grid(row=5, column=2)
    
    clear = tk.Button(gui, text='Clear', command=clear, **btn_params)
    clear.grid(row=5, column=0)
    
    # Start the GUI
    gui.mainloop()