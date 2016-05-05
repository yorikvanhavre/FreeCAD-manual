## Using spreadsheets

FreeCAD features another interesting workbench to explore: the [Spreadsheet Workbench](http://www.freecadweb.org/wiki/index.php?title=Spreadsheet_Module). This workbench allows to create [spreadsheets](https://en.wikipedia.org/wiki/Spreadsheet) such as those made with [Excel](https://en.wikipedia.org/wiki/Microsoft_Excel) or [LibreOffice](https://en.wikipedia.org/wiki/OpenOffice.org_Calc) directly in FreeCAD. These spreadsheets can then be populated with data extracted from your model, and can also perform a series of calculations between values. Spreadsheets can be exported as CSV files, which can be imported in any other spreadsheet application.

In FreeCAD, however, spreadsheets have an additional utility: Their cells can receive a name, and can then be referenced by any field supported by the [expressions engine](http://www.freecadweb.org/wiki/index.php?title=Expressions). This turns spreadsheets into powerful control structures, where the values inserted in specific cells can drive dimensions of the model. There is only one thing to keep in mind, as FreeCAD prohibits circular dependencies between objects, a same spreadsheet cannot be used to set a property of an object and at the same time retrieve a property value from the same object. That would make the spreadsheet and the object depending on each other.

In the following example, we will create a couple of objects, retrieve some of their properties in a spreadsheet, then use the spreadsheet to directly drive properties of other objects.

* Start by switching to the [Part Workbench](http://www.freecadweb.org/wiki/index.php?title=Part_Workbench), and create a couple of objects: a ![icon](http://www.freecadweb.org/wiki/images/thumb/a/a5/Part_Box.png/16px-Part_Box.png) [box](http://www.freecadweb.org/wiki/index.php?title=Part_Box), a ![icon](http://www.freecadweb.org/wiki/images/thumb/d/d4/Part_Cylinder.png/16px-Part_Cylinder.png) [cylinder](http://www.freecadweb.org/wiki/index.php?title=Part_Cylinder) and a ![icon](http://www.freecadweb.org/wiki/images/thumb/4/4b/Part_Sphere.png/16px-Part_Sphere.png) [sphere](http://www.freecadweb.org/wiki/index.php?title=Part_Sphere).
* Edit their **Placement** property (or use the ![icon](http://www.freecadweb.org/wiki/images/thumb/c/c5/Draft_Move.png/16px-Draft_Move.png) [Draft Move](http://www.freecadweb.org/wiki/index.php?title=Draft_Move) tool) to place them a little apart, so we can watch better the effects of what we'll do:

![the 3 objects](http://www.freecadweb.org/wiki/images/c/c1/Exercise_spreadsheet_01.jpg)

* Now, lt's extract some information about these objects. Switch to the [Spreadsheet Workbench](http://www.freecadweb.org/wiki/index.php?title=Spreadsheet_Module)
* Press the ![icon](http://www.freecadweb.org/wiki/images/thumb/c/cb/Spreadsheet_Create.png/16px-Spreadsheet_Create.png) **New Spreadsheet** button
* Double-click the new Spreadsheet object in the tree view. The spreadsheet editor opens:

![the spreadsheet editor](http://www.freecadweb.org/wiki/images/e/e5/Exercise_spreadsheet_02.jpg)

The spreadsheet editor of FreeCAD, although it is not as complete and powerful as the more complete spreadsheet applications we listed above, has nevertheless most of the basic tools and functions that are commonly used, such as the possibility to change the aspect of the cells (size, color, alignment), join and split cells, use formulas such as **=2+2**, or reference other cells with **=B1**. 

In FreeCAD, to these common behaviours, has been added one very interesting: The possibility to reference not only other cells, but other objects from the document.

**Read more**

* The Spreadsheet Workbench: http://www.freecadweb.org/wiki/index.php?title=Spreadsheet_Module
* The Expressions engine: http://www.freecadweb.org/wiki/index.php?title=Expressions
