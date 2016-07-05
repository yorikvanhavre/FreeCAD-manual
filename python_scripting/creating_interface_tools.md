## Creating interface tools

In the last two chapters, we saw how to [create Part geometry](creating_and_manipulating_geometry.md) and [create parametric objects](creating_parametric_objects.md). One last piece is missing to gain full control over FreeCAD: Create tools that will interact with the user.

In many situations, it is not very user-friendly to construct an object with zero-values, like we did with the rectangle in the previous chapter, and then ask the user to fill in the Height and Width values in the Properties panel. This works for a very small number of objects, but will become very tedious if you have a lot of rectangles to make. A better way would be to be able to already give the Height and Width when creating the rectangle.

Python offers a basic tool to have the user enter text on screen:

```
text = raw_input("Height of the rectangle?")
print("The entered height is ",text)
```

However, this requires a running Python console, and when running our code from a macro, we are not always sure that the Python console will be turned on on the user's machine.

The [Graphical User Interface](https://en.wikipedia.org/wiki/Graphical_user_interface), or GUI, that is, all the part of FreeCAD that is displayed on your screen (the menu, toolbars, 3D view, etc), is all there for that purpose: interact with the user. FreeCAD's interface is built with [Qt](https://en.wikipedia.org/wiki/Qt_(software)), a very common GUI toolkit that offers a big range of tools such as dialog boxes, buttons, labels, text input boxes or pull-down menus (all these are generically called "widgets").

The Qt tools are very easy to use from Python, thanks to a Python module called [Pyside](https://en.wikipedia.org/wiki/PySide) (there are several other Python modules to communicate with Qt from Python too). This module allows you to create and interact with widgets, read what the user did with them (what was filled in text boxes) or do things when, for example, a button was pressed.

Qt also provides another interesting tool called [Qt Designer](http://doc.qt.io/qt-4.8/designer-manual.html), which is today embedded inside a bigger application called [Qt Creator](https://en.wikipedia.org/wiki/Qt_Creator). It allows to design dialog boxes and interface panels graphically, instead of having to code them manually.

**Read more**

* Qt Creator: https://en.wikipedia.org/wiki/Qt_Creator
