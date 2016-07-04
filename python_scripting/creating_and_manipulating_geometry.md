## Creating and manipulating geometry

In the previous chapters, we learned about the different workbenches of FreeCAD, and that each of them implements its own tools and geometry types. The same concepts applies when working from Python code.

We also saw that the big majority of the FreeCAD workbenches depend on a very fundamental one: the [Part Workbench](http://www.freecadweb.org/wiki/index.php?title=Part_Workbench). In fact, may other workbenches, such as [Draft](http://www.freecadweb.org/wiki/index.php?title=Draft_Module) or [Arch](http://www.freecadweb.org/wiki/index.php?title=Arch_Module), do exactly what we will do in this chapter: They use Python code to create and manipulate Part geometry.

So the forst thing we need to do to work with Part geometry, is to do the Python equivalent to switching to the Part Workbench: import the Part module:

`import Part`

Take a minute to explore the contents of the Part module, by typing `Part.` and browsing through the different methods offered there. The Part module offers several convenience fuctions such as makeBox, makeCircle, etc... which will instantly build an object for you. Try this, for example:

`Part.makeBox(3,5,7)`


**Read more**:

* The Part Workbench: http://www.freecadweb.org/wiki/index.php?title=Part_Workbench
