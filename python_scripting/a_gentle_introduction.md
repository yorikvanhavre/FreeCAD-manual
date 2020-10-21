## A gentle introduction

[//]: # (Per the Python style guide; The name of our favorite programming language is always capitalized. )

[//]: # (see: https://docs.python.org/3.1/documenting/style.html)

[Python](https://en.wikipedia.org/wiki/Python_%28programming_language%29) is a widely popular, open-source programming language, very often used as a scripting language, embedded in applications, as is the case with FreeCAD. It also has a series of features that makes it specially interesting for us FreeCAD users: It is very easy to learn, specially for people who have never programmed before.  It is embedded in many other applications, which makes it a very valuable tool to learn.  You will be able to use it in many other applications, such as [Blender](http://www.blender.org), [Inkscape](http://www.inkscape.org) or [GRASS](http://grass.osgeo.org/).

FreeCAD makes extensive use of Python. With it, you can access and control almost any feature of FreeCAD. You can, for example, create new objects, modify their geometry, analyze their contents, or even create new interface controls, tools and panels. Some workbenches of FreeCAD and most of the addon workbenches are fully programmed in Python. FreeCAD has an advanced Python console, available from menu **View→Panels→Python console**. It is often useful to perform operations for which there is no toolbar button yet, or to check shapes for problems, or to perform repetitive tasks:

![the Python console](http://www.freecadweb.org/wiki/images/c/cf/Exercise_python_01.jpg)

But the Python console also has another very important use: Every time you press a toolbar button, or perform other operations in FreeCAD, some Python code is printed in the console and executed. By leaving the Python console open, you can literally see the Python code unfold as you work, and in no time, almost without knowing it, you will be learning some Python language.

FreeCAD also has a [macros system](http://www.freecadweb.org/wiki/index.php?title=Macros), which allows you to record actions to be replayed later. This system also uses the Python console, by simply recording everything that is done in it.

In this chapter, we will discover very generally the Python language. If you are interested in learning more, the FreeCAD documentation wiki has an extensive section related to [Python programming](http://www.freecadweb.org/wiki/index.php?title=Power_users_hub).

### Writing Python code

There are two easy ways to write Python code in FreeCAD: From the Python console (menu **View → Panels → Python Console**), or from the Macro editor (menu **Tools → Macros → New**). In the console, you write Python commands one by one, which are executed when you press return, while the macros can contain a more complex script made of several lines, which is executed only when the macro is launched from the same Macros window.

In this chapter, you will be able to use both methods, but it is highly recommended to use the Python Console, since it will immediately inform you of any typing error.

If this is the first time you are coding in Python, consider reading this short [Introduction to Python](http://www.freecadweb.org/wiki/index.php?title=Introduction_to_Python) before going further, it will make the basic concepts of Python clearer.

### Manipulating FreeCAD objects

Let's start by creating a new empty document:

`doc = FreeCAD.newDocument()`

If you type this in the FreeCAD Python console, you will notice that as soon as you type "FreeCAD." (the word FreeCAD followed by a dot), a windows pops up, allowing to quickly autocomplete the rest of your line. Even better, each entry in the autocomplete list has a tooltip explaining what it does. This makes it very easy to explore the functionality available. Before choosing "newDocument", have a look at the other options available.

![The autocomplete mechanism of the FreeCAD Python console](http://www.freecadweb.org/wiki/images/e/e2/Exercise_python_02.jpg)

As soon as you press **Enter** our new document will be created. This is similar to pressing the "new document" button on the toolbar. In Python, the dot is used to indicate something that is contained inside something else (newDocument is a function that is inside the FreeCAD module). The window that pops up therefore shows you everything that is contained inside "FreeCAD". If you would add a dot after newDocument, instead of the parentheses, it would show you everything that is contained inside the newDocument function. The parentheses are mandatory when you are calling a Python function, such as this one. We will illustrate that better below.

Now let's get back to our document. Let's see what we can do with it:

`doc.`

Explore the available options. Usually names that begin with a capital letter are attributes, they contain a value, while names that begin with small letter are functions (also called methods), they "do something". Names that begin with an underscore are usually there for the internal working of the module, and you shouldn't care about them. Let's use one of the methods to add a new object to our document:

`box = doc.addObject("Part::Box","myBox")`

Our box is added in the tree view, but nothing happens in the 3D view yet, because when working from Python, the document is never recomputed automatically. We must do that manually, whenever we need:

`doc.recompute()`

Now our box appeared in the 3D view. Many of the toolbar buttons that add objects in FreeCAD actually do two things: add the object, and recompute. If you turned on the "show script commands in Python console" option above, try now adding a sphere with the appropriate button in the Part Workbench, and you will see the multiple lines of Python code being executed one after the other.

You can get a list of all possible object types like Part::Box:

`doc.supportedTypes()`

Now let's explore the contents of our box:

`box.`

You'll immediately see a couple of very interesting things such as:

`box.Height`

This will print the current height of our box. Now let's try to change that:

`box.Height = 5`

If you select your box with the mouse, you will see that in the properties panel, under the **Data** tab, our **Height** property appears with the new value. All properties of a FreeCAD object that appear in the **Data** and **View** tabs are directly accessible by Python too, by their names, like we did with the Height property. Data properties are accessed directly from the object itself, for example:

`box.Length`

View properties are stored inside a **ViewObject**. Each FreeCAd object possesses a ViewObject, which stores the visual properties of the object. When running FreeCAD without its Graphical Interface (for example when launching it from a terminal with the -c command line option, or using it from another Python script), the ViewObject is not available, since there is no visual at all.

For example, to access the line color of our box:

`box.ViewObject.LineColor`

### Vectors and Placements

Vectors are a very fundamental concept in any 3D application. It is a list of 3 numbers (x, y and z), describing a point or position in the 3D space. A lot of things can be done with vectors, such as additions, subtractions, projections and much more. In FreeCAD vectors work like this:

```
myvec = FreeCAD.Vector(2,0,0)
print(myvec)
print(myvec.x)
print(myvec.y)
othervec = FreeCAD.Vector(0,3,0)
sumvec = myvec.add(othervec)
print(sumvec)
```

Another common feature of FreeCAD objects is their **Placement**. As we saw in earlier chapters, each object has a Placement property, which contains the position (Base) and orientation (Rotation) of the object. It is easy to manipulate from Python, for example to move our object:

```
print(box.Placement)
print(box.Placement.Base)
box.Placement.Base = sumvec
otherpla = FreeCAD.Placement()
otherpla.Base = FreeCAD.Vector(5,5,0)
box.Placement = otherpla
```

Placement can be a difficult concept to grasp at first. Calling FreeCAD.Placement, you can optionally enter in position, rotation, and center values. This will generate you a placement matrix.

For example,

```
yaw = 3.5
pos = App.Vector(0, 0, 0)
rot = App.Rotation(yaw, 0, 0)
center = App.Vector(0, 0, 0)
newplace = App.Placement(pos, rot, center)
```

After that, you can alter your placement matrix by multiplying it,

```
pitch = 2.3
rot = App.Rotation(0, pitch, 0)
newplace = App.Placement(pos, rot, center).multiply(newplace)
```

**Read more**

* Python: https://www.python.org/
* Working with Macros: http://www.freecadweb.org/wiki/index.php?title=Macros
* Introduction to Python scripting: http://www.freecadweb.org/wiki/index.php?title=Introduction_to_Python
* Using Python in FreeCAD: http://www.freecadweb.org/wiki/index.php?title=Python_scripting_tutorial
* The Python scripting wiki hub: http://www.freecadweb.org/wiki/index.php?title=Power_users_hub
