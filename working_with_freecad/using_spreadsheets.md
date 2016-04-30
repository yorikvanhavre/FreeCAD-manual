## Using spreadsheets

FreeCAD features another interesting workbench to explore: the [Spreadsheet Workbench](http://www.freecadweb.org/wiki/index.php?title=Spreadsheet_Module). This workbench allows to create [spreadsheets](https://en.wikipedia.org/wiki/Spreadsheet) such as those made with [Excel](https://en.wikipedia.org/wiki/Microsoft_Excel) or [LibreOffice](https://en.wikipedia.org/wiki/OpenOffice.org_Calc) directly in FreeCAD. These spreadsheets can then be populated with data extracted from your model, and can also perform a series of calculations between values. Spreadsheets can be exported as CSV files, which can be imported in any other spreadsheet application.

In FreeCAD, however, spreadsheets have an additional utility: Their cells can receive a name, and can then be referenced by any field supported by the [expressions engine](http://www.freecadweb.org/wiki/index.php?title=Expressions). This turns spreadsheets into powerful control structures, where the values inserted in specific cells can drive dimensions of the model. There is only one thing to keep in mind, as FreeCAD prohibits circular dependencies between objects, a same spreadsheet cannot be used to set a property of an object and at the same time retrieve a property value from the same object. That would make the spreadsheet and the object depending on each other.

In the following example, we will create a couple of objects, retrieve some of their properties in a spreadsheet, then use the spreadsheet to directly drive properties of other objects.

* Start by switching to the [Part Workbench](http://www.freecadweb.org/wiki/index.php?title=Part_Workbench), and create a couple of objects: a ![icon](http://www.freecadweb.org/wiki/images/thumb/a/a5/Part_Box.png/16px-Part_Box.png) [box](http://www.freecadweb.org/wiki/index.php?title=Part_Box), a ![icon](http://www.freecadweb.org/wiki/images/thumb/d/d4/Part_Cylinder.png/16px-Part_Cylinder.png) [cylinder](http://www.freecadweb.org/wiki/index.php?title=Part_Cylinder) and a ![icon](http://www.freecadweb.org/wiki/images/thumb/4/4b/Part_Sphere.png/16px-Part_Sphere.png) [sphere](http://www.freecadweb.org/wiki/index.php?title=Part_Sphere).

**Read more**

* The Spreadsheet Workbench: http://www.freecadweb.org/wiki/index.php?title=Spreadsheet_Module
* The Expressions engine: http://www.freecadweb.org/wiki/index.php?title=Expressions
