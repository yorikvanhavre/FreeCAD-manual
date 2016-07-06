## Creating interface tools

In the last two chapters, we saw how to [create Part geometry](creating_and_manipulating_geometry.md) and [create parametric objects](creating_parametric_objects.md). One last piece is missing to gain full control over FreeCAD: Create tools that will interact with the user.

In many situations, it is not very user-friendly to construct an object with zero-values, like we did with the rectangle in the previous chapter, and then ask the user to fill in the Height and Width values in the Properties panel. This works for a very small number of objects, but will become very tedious if you have a lot of rectangles to make. A better way would be to be able to already give the Height and Width when creating the rectangle.

Python offers a basic tool to have the user enter text on screen:

```
text = raw_input("Height of the rectangle?")
print("The entered height is ",text)
```

However, this requires a running Python console, and when running our code from a macro, we are not always sure that the Python console will be turned on on the user's machine.

The [Graphical User Interface](https://en.wikipedia.org/wiki/Graphical_user_interface), or GUI, that is, all the part of FreeCAD that is displayed on your screen (the menu, toolbars, 3D view, etc), is all there for that purpose: interact with the user. FreeCAD's interface is built with [Qt](https://en.wikipedia.org/wiki/Qt_(software)), a very common open-source GUI toolkit that offers a big range of tools such as dialog boxes, buttons, labels, text input boxes or pull-down menus (all these are generically called "widgets").

The Qt tools are very easy to use from Python, thanks to a Python module called [Pyside](https://en.wikipedia.org/wiki/PySide) (there are several other Python modules to communicate with Qt from Python too). This module allows you to create and interact with widgets, read what the user did with them (what was filled in text boxes) or do things when, for example, a button was pressed.

Qt also provides another interesting tool called [Qt Designer](http://doc.qt.io/qt-4.8/designer-manual.html), which is today embedded inside a bigger application called [Qt Creator](https://en.wikipedia.org/wiki/Qt_Creator). It allows to design dialog boxes and interface panels graphically, instead of having to code them manually. In this chapter, we will use Qt Creator to desig a panel widget that we will use in the **Task** panel of FreeCAD. So you will need to download and install Qt Creator from its [official page](https://www.qt.io/ide/) if you are on Windows or Mac (on Linux it will usually be available from your software manager application).

In the following exercise, we will first create a panel with Qt Creator that asks for length, width and height values, then we will create a Python class around it, that will read the values entered by the user from the panel, and create a box with the given dimensions. This Python class will then be used by FreeCAD to display and control the task panel:

![the panel](http://www.freecadweb.org/wiki/images/0/0b/Exercise_python_07.jpg)

Let's start by creating the widget. Start Qt Creator, then menu **File -> New File or Project -> Files and Classes -> Qt -> Qt Designer Form -> Dialog without buttons**. Click **Next**, give it a filename to save, click **Next**, leave all project fields to their default value ("<none>"), and **Create**. FreeCAD's Task system will automatically add OK/Cancel buttons, that's why we chose here a dialog without buttons.

![qt creator started](http://www.freecadweb.org/wiki/images/9/91/Exercise_python_06.jpg)

* Find the **Label** in the list in the left panel, and drag it onto the canvas of our widget. Double-click the recent placed Label, and change its text to **Length**.
* Right-click the widget canvas, and choose **Lay out-> Lay out in a Grid**. This will turn our widget into a grid with currently only one cell, occupied by ourfirst label. We can now add the next items at the left, right, top or bottom of our first label, and the grid wil lexpand automatically.
* Add two more labels below the first one, and change their text to Width and Height:

![other labels](http://www.freecadweb.org/wiki/images/c/cf/Exercise_python_08.jpg)

* Now place 3 **Double Spin Box** widgets next to our Length, Width and Height labels. For each of them, in the lower left panel, which shows all the available settings for the selected widget, locate **Suffix** and set their suffix to **mm**:

![the spin boxes](http://www.freecadweb.org/wiki/images/a/aa/Exercise_python_09.jpg)

* FreeCAD has a more advanced widget, that can handle different units, but that is not available in Qt Creator by default (but can be compiled)



**Read more**

* Qt Creator: https://en.wikipedia.org/wiki/Qt_Creator
* Installing Qt Creator: https://www.qt.io/ide/
