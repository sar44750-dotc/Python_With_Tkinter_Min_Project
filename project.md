Ahh, got it — you want the **actual Python code** for the **previous project (Calculator with Tkinter)** 👍
Sorry about that, let’s fix it properly.

---

## 🧮 Calculator Application – Python + Tkinter (FULL CODE)

Create a file named **`calculator.py`** and paste this code:

```python
import tkinter as tk
from tkinter import messagebox

# Main window
root = tk.Tk()
root.title("Calculator")
root.geometry("300x400")
root.resizable(False, False)

# Entry field
entry = tk.Entry(root, width=18, font=("Arial", 18), borderwidth=5, relief="ridge", justify="right")
entry.grid(row=0, column=0, columnspan=4, padx=10, pady=10)

# Functions
def button_click(value):
    entry.insert(tk.END, value)

def clear():
    entry.delete(0, tk.END)

def calculate():
    try:
        result = eval(entry.get())
        entry.delete(0, tk.END)
        entry.insert(0, result)
    except:
        messagebox.showerror("Error", "Invalid Input")

# Buttons layout
buttons = [
    '7', '8', '9', '/',
    '4', '5', '6', '*',
    '1', '2', '3', '-',
    '0', '.', '=', '+'
]

row = 1
col = 0

for btn in buttons:
    if btn == '=':
        action = calculate
    else:
        action = lambda x=btn: button_click(x)

    tk.Button(
        root,
        text=btn,
        width=5,
        height=2,
        font=("Arial", 14),
        command=action
    ).grid(row=row, column=col, padx=5, pady=5)

    col += 1
    if col > 3:
        col = 0
        row += 1

# Clear button
tk.Button(
    root,
    text="C",
    width=22,
    height=2,
    font=("Arial", 14),
    command=clear
).grid(row=row, column=0, columnspan=4, padx=5, pady=5)

# Run app
root.mainloop()
```

---

## 📂 Project Files

```
Calculator-App/
 ┣ 📄 calculator.py
 ┗ 📄 README.md
```

---

## ▶️ How to Run

```bash
python calculator.py
```

 
