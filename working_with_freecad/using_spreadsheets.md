## Using spreadsheets

FreeCAD features another interesting workbench to explore: the [Spreadsheet Workbench](http://www.freecadweb.org/wiki/index.php?title=Spreadsheet_Module). This workbench allows you to create [spreadsheets](https://en.wikipedia.org/wiki/Spreadsheet) such as those made with [Excel](https://en.wikipedia.org/wiki/Microsoft_Excel) or [LibreOffice](https://en.wikipedia.org/wiki/OpenOffice.org_Calc) directly in FreeCAD. These spreadsheets can then be populated with data extracted from your model, and can also perform a series of calculations between values. Spreadsheets can be exported as CSV files, which can be imported in any other spreadsheet application.

In FreeCAD, however, spreadsheets have an additional utility: Their cells can receive a name, and can then be referenced by any field supported by the [expressions engine](http://www.freecadweb.org/wiki/index.php?title=Expressions). This turns spreadsheets into powerful control structures, where the values inserted in specific cells can drive dimensions of the model. There is only one thing to keep in mind, as FreeCAD prohibits circular dependencies between objects, a same spreadsheet cannot be used to set a property of an object and at the same time retrieve a property value from the same object. That would make the spreadsheet and the object depending on each other.

In the following example, we will create a couple of objects, retrieve some of their properties in a spreadsheet, then use the spreadsheet to directly drive properties of other objects.

We will assume the reader has worked through the previous chapters and we'll not provide a lot of detail that's been covered previously

### Reading properties

* Start by switching to the [Part Workbench](http://www.freecadweb.org/wiki/index.php?title=Part_Workbench), and create a couple of objects: a ![icon](http://www.freecadweb.org/wiki/images/thumb/a/a5/Part_Box.png/16px-Part_Box.png) [box](http://www.freecadweb.org/wiki/index.php?title=Part_Box), a ![icon](http://www.freecadweb.org/wiki/images/thumb/d/d4/Part_Cylinder.png/16px-Part_Cylinder.png) [cylinder](http://www.freecadweb.org/wiki/index.php?title=Part_Cylinder) and a ![icon](http://www.freecadweb.org/wiki/images/thumb/4/4b/Part_Sphere.png/16px-Part_Sphere.png) [sphere](http://www.freecadweb.org/wiki/index.php?title=Part_Sphere).
* Edit their **Placement** property (or use the ![icon](http://www.freecadweb.org/wiki/images/thumb/c/c5/Draft_Move.png/16px-Draft_Move.png) [Draft Move](http://www.freecadweb.org/wiki/index.php?title=Draft_Move) tool) to space them out, so we can see the effects of our changes:

![the 3 objects](http://www.freecadweb.org/wiki/images/c/c1/Exercise_spreadsheet_01.jpg)

* Now, lt's extract some information about these objects. Switch to the [Spreadsheet Workbench](http://www.freecadweb.org/wiki/index.php?title=Spreadsheet_Module)
* Press the ![icon](http://www.freecadweb.org/wiki/images/thumb/c/cb/Spreadsheet_Create.png/16px-Spreadsheet_Create.png) **New Spreadsheet** button
* Double-click the new Spreadsheet object in the tree view. The spreadsheet editor opens in another tab of the geometry window:

![the spreadsheet editor](http://www.freecadweb.org/wiki/images/e/e5/Exercise_spreadsheet_02.jpg)

The spreadsheet editor of FreeCAD, although it is not as complete and powerful as the spreadsheet applications above, has the basic tools and functionality commonly needed.  For example you can change the cell properties (size, color, alignment), join and split cells, use formulas such as **=2+2**, or reference other cells with **=B1**. 

One more very interesting feature has been added to this basic functionality: The possibility to reference not only other cells, but other objects from the document, and retrieve values from their properties. For example, let's retrieve a couple of properties from the 3 objects we created above. Properties are what we can see in the properties editor window, under the **Data** tab, when an object is selected.

* Let's start by entering some text in cells A1, A2 and A3, as a reminder for us humans, for example **Cube Length**, **Cylinder Radius** and **Sphere Radius**.  Enter text, just as you would any spreadsheet program, click in the desired cell and then click on the "Contents" field above the spreadsheet and enter the desired text, or double-click a cell.
* Now let's retrieve the actual length of our cube. In cell B1, type **=Cube.Length**. You will notice that the spreadsheet has an auto completion mechanism, which is actually the same as the expression editor we used in the previous chapter.
* Do the same for cell B2 (**=Cylinder.Radius**) and B3 (**=Sphere.Radius**).

![entering expressions](http://www.freecadweb.org/wiki/images/3/3e/Exercise_spreadsheet_03.jpg)

* Although these results are expressed with their units, the values can be manipulated as any number, try for example entering in cell C1: **=B1*2**.
* We can now change one of these values in the properties editor, and the change will be immediately reflected in the spreadsheet. For example, let's change the length of our cube to **20mm**:

![changing values](http://www.freecadweb.org/wiki/images/8/8b/Exercise_spreadsheet_04.jpg)

The [Spreadsheet Workbench](http://www.freecadweb.org/wiki/index.php?title=Spreadsheet_Module) page will describe more in detail all the possible operations and functions that you can use in spreadsheets.

### Writing properties

Another very interesting use of the Spreadsheet Workbench in FreeCAD is the inverse of what we've been doing: Instead of reading the values of properties of 3D objects, we can also assign values to these objects. Remember, however, one of the fundamental rules of FreeCAD: **Circular dependencies are forbidden**. We therefore can not use the same spreadsheet to read **and** write values to a 3D object. That would make the object depend on the spreadsheet, which would also depend on the object. Instead, we will create another spreadsheet.

* We can now close the spreadsheet tab (small x in the spreadsheet tab of the geometry window). This is not a requirement, multiple open spreadsheets are no problem.
* Press the ![icon](http://www.freecadweb.org/wiki/images/thumb/c/cb/Spreadsheet_Create.png/16px-Spreadsheet_Create.png) **New Spreadsheet** button again
* Change the name of the new spreadsheet to something more meaningful, such as **Input** (do this by right-clicking the new spreadsheet object, and choosing **Rename**).
* Double-click the Input spreadsheet to open the spreadsheet editor.
* In cell A1, let's put a descriptive text, for example: "Cube dimensions"
* In cell B1, write **=5mm** (using the = sign makes sure the value is interpreted as non-text).
* Now to be able to use this value outside the spreadsheet, we need to give a name, or alias, to the B1 cell.  Right-click the cells, click **Properties** and select the **Alias** tab. Give it a name, such as **cubedims**:

![setting alias](http://www.freecadweb.org/wiki/images/0/08/Exercise_spreadsheet_05.jpg)

* Press **OK**, then close the spreadsheet tab (Right click on the spreadsheet tab in the bottom of the geometry window, select close from the list.  Spreadsheet still exists in the Model tree.)
* Select the cube object
* In the properties editor, click the little ![icon](http://www.freecadweb.org/wiki/images/thumb/3/38/Bound-expression-unset.png/16px-Bound-expression-unset.png) **expression** icon at the right side of the **Length** field. This will open then [expressions editor](http://www.freecadweb.org/wiki/index.php?title=Expressions), where you can write **Spreadsheet001.cubedims**. (You're first inclination is to use the name "Input," however for now use "Spreadsheet001," more later.)  You should note the cube shape change in the dimension you entered.  Repeat this for Height and Width:

![using spreadsheet aliases](http://www.freecadweb.org/wiki/images/8/8a/Exercise_spreadsheet_06.jpg)

You might wonder why we used "Spreadsheet001" instead of "Input" in the expression above. This is because each object, in a FreeCAD document, has an **internal name**, (e.g. Spreadsheet001) which is unique in the document, and a **label**, (e.g. Input) which appears in the tree view. If you uncheck the appropriate option in the preferences settings, FreeCAD will allow you to give the same label to more than one object. All operations that must identify an object with absolutely certainty, will use the unique internal name instead of the label, which could designate more than one object. The easiest way to know the internal name of an object is by keeping the **Selection panel** (top menu **View** → **Panels** → **Selection view**) open, it will always indicate the internal name of a selected object:

![checking real names](http://www.freecadweb.org/wiki/images/7/74/Exercise_spreadsheet_07.jpg)

By using cell aliases in spreadsheets, we are able to use a spreadsheet to store "master values" in a FreeCAD document. This can be used, for example, to have a master model of certain dimensions, and to store these dimensions in a spreadsheet. It becomes then very easy to produce another child model with different dimensions.  It is just a matter of opening the file and changing a couple of dimensions in the spreadsheet and saving the child file to a new name.

Finally, note that the constraints inside a sketch can also receive the value of a spreadsheet cell:

![setting constraints](http://www.freecadweb.org/wiki/images/6/63/Exercise_spreadsheet_08.jpg)

You can also give aliases to dimensional constraints (horizontal, vertical or distance)  in a sketch (you can then use that value from outside the sketch as well):

![setting constraint alias](http://www.freecadweb.org/wiki/images/a/a7/Exercise_spreadsheet_09.jpg)

**Download**

* The file produced in this exercise: https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/spreadsheet.FCStd

**Read more**

* The Spreadsheet Workbench: http://www.freecadweb.org/wiki/index.php?title=Spreadsheet_Module
* The Expressions engine: http://www.freecadweb.org/wiki/index.php?title=Expressions
