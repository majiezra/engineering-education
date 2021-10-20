
### How to create a font chooser app using python 
A font picker is a simple application that allows you to browse through all the fonts installed on your computer, and filter down your options to find the ideal one for your project.

The Tkinter Python library will be used to construct a font chooser application in this tutorial.

### Table of content.
- Prerequisite
- Tkinter
- Graphical User Interface
- Creating a font chooser app
- Conclusion
- Reference

### Prerequisite
To follow along with this tutorial, you will need to have:

- [Python3](https://www.python.org/downloads/) installed on your computer system.
- A code editor, i use [Pycharm](https://www.jetbrains.com/pycharm/download/).

### Tkinter
Python's standard GUI library is Tkinter. When Python and Tkinter are integrated, creating graphical user interfaces becomes much faster and easier. 

Tkinter provides geometric widget configuration, which organizes widgets in parent windows for grahical user interface.

There are three geometry manager classes in Tkinter. These are:

- `.pack()` : It's used to organize widgets in blocks before they're placed in parent widgets.
- `.grid()` : Before inserting widgets in the parent widget, grid() is used to organize them into a table-like layout.
- `.place()` : This function is used to organize widgets by placing them in precise positions as specified by the programmer.

Tkinter is a fantastic tool for creating graphical user interfaces and applications in python and we will be using it to build the font chooser application.

You can install Tkinter by using the `pip` command.

```python
pip install tk
```

### The graphical user interface
The graphical user interface is the most common type of user interfaces. One can interact with these interfaces by pointing and clicking on graphics or icons with a mouse, trackpad, or other peripherals.

#### Advantages of the graphical user interface
- It is simpler to use compared to Command Line Interface.
- There is no need to memorize the command lists as it is easy to visualize and remember.
- It allows multitasking of more than applications and programs to run simultaneously. 
- It provides many exceptional support services.

#### Disadvantages of the graphical user interface
It consumes a lot of computer memory, elements like icon and fonts must be loaded.

Additional system resources are required to load video, mouse, and other drivers, while a command line interface doesn't require so much memory to to run on a computer system.

### Creating a font chooser app
In our code editor, we'll make a new file called `font.py`, where we'll write our code.

Let's begin by importing Tkinter as well as fonts from the tkinter library.

```python
from tkinter import *
from tkinter import font

root = Tk()

root.title('maji.com - Font Chooser App')
root.iconbitmap('c:/gui/maji.ico')
root.geometry("500x400")
```

To start, first, we will create a root widget and this root widget is a window with a title bar. This widget has to be created first, and it is called the root widget, after creating the root widget, the programmer can then create other widgets.

Then we give our font app a name (I used `maji.ico`. You can use your own name if you want to customize the app.). Then we set the size of the application.

```python
def font_chooser(a):
        user_font.config(family=my_listbox.get(my_listbox.curselection()))
```

Then we write the `font_chooser` function, which includes defining the font function and configuring the `Listbox` to retrieve the system's current font selection.

```python
user_font = font.Font(family="Helvetica", size="30")

my_frame = Frame(root, width=490, height=285)
my_frame.pack(pady=10)
my_frame.grid_propagate(False)
my_frame.columnconfigure(0, weight=10)
```

Then we specify our font by setting our `font_variable` to a Helvetica typeface with a size of 30. Then a frame is created by defining the `my_frame` variable, which specifies the width and height.

The `.grid` function is also used to freeze the frame and prevent the size of the `Listbox` from changing unnecessarily each time a new font is picked from the font chooser app.

```python
user_text = Text(my_frame, font=user_font)
user_text.grid(row=1, column=1)
user_text.grid_rowconfigure(0, weight=1)
user_text.grid_columnconfigure(0, weight=1)

user_listbox = Listbox(root, selectmode=SINGLE, width=90)
user_listbox.pack()
```

By defining the `user_text` variable, we can add the textbox. We do this by putting the defined variable in a frame and utilising our font to make the font size dynamic.

We utilize the `.grid` function to prevent the font app from resizing abnormally, and we set the row and column weights to 1 to ensure that it evenly distributes any additional space in the row and column.

We create a `Listbox` by setting the `my_listbox` variable to a listbox with a single-mode selection, which allows us to choose only one font at a time while still specifying the width size.

```python
for f in font.families():
        my_listbox.insert('end', f)
my_listbox.bind('<ButtonRelease-1>', font_chooser)
root.mainloop()
```

We use a `for` loop to iterate over the `font.families` sequence to add font families to the already formed `Listbox`, and then use the `.bind` function to bind the `Listbox`.

`mainloop()` is the method that we will use to run the font chooser application. It will allow the application to run continuously and indefinitely until the user decides to end the program by closing the window or using the Escape key on the keyboard.

And the font chooser interface will look like this:
![fontapp image](/engineering-education/how-to-create-font-chooser-application/fontchooser.png)

### Conclusion
In this tutorial, we reviewed the role of Tkinter in data science and built a font chooser application.

### Reference
[Python GUI programming with Tkinter](https://www.perlego.com/book/721869/python-gui-programming-with-tkinter-pdf) by Alan D Moore

