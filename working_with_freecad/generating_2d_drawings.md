## Generating 2D drawings

When your model cannot be printed or milled directly by a machine, for example it is too big (a building) or it requires manual assembly after the pieces are ready, you will usually need to explain to another person how to do that. In technical fields (engineering, architecture, etc), this is usually done with drawings, that are handed over to the person responsible for assembling the final product, that will explain how to do it.

Typical examples are [Ikea instructions](http://www.ikea.com/ms/en_US/customer_service/assembly_instructions.html), [architectural drawings](https://en.wikipedia.org/wiki/Architectural_drawing) or [blueprints](https://en.wikipedia.org/wiki/Blueprint). These drawings usually contain not only the drawing itself, but also many annotations, such as texts, dimensions, numbers, symbols that will help other people to understand what needs to be done and how.

In FreeCAD, the workbench responsible for making such drawings is the [Drawing Workbench](http://www.freecadweb.org/wiki/index.php?title=Drawing_Module). 

The Drawing Workbench allows you to create sheets, which can be blank or use a pre-made [template](http://www.freecadweb.org/wiki/index.php?title=Drawing_templates) to already have a series of items on the sheet, such as borders and title. On these sheets, you can then place [views](http://www.freecadweb.org/wiki/index.php?title=Drawing_View) of the 3D objects you modeled previously, and configure how these views must appear on the sheet. Finally, thanks to an [addon](https://github.com/FreeCAD/FreeCAD-addons) called [Drawing Dimensioning Workbench](https://github.com/hamish2014/FreeCAD_drawing_dimensioning), you can also place all kinds of annotations on the sheet, such as dimensions, texts, and other usual symbols commonly used in technical drawings.

Drawing sheets, once complete, can be printed or exported as [SVG](https://en.wikipedia.org/wiki/Scalable_Vector_Graphics), PDF or [DXF](https://en.wikipedia.org/wiki/AutoCAD_DXF) files.

In the following exercise, we will see how to create a simple drawing of a chair model found in the [FreeCAD library](https://github.com/FreeCAD/FreeCAD-library) (Furniture -> Chairs -> IkeaChair). The FreeCAD library can easily be added to your FreeCAD installation (refer to the [installing](../discovering_freecad/installing.md#installing-additional-content) chapter of this manual), or you can simply download the model from the library webpage, or via the direct link provided at the bottom of this chapter.

![the drawing exercise](http://www.freecadweb.org/wiki/images/4/40/Exercise_drawing_01.jpg)

* Load the IkeaChair file from the library. You can choose between the .FCStd version, which will load the full modeling history, or the .step version, which will create only one object, without the history. Since we won't need to model any further now, it is best to choose the .step version, as it will be easier to manipulate.

![the Parts library](http://www.freecadweb.org/wiki/images/6/69/Parts_library.jpg)

* Switch to the [Drawing Workbench](http://www.freecadweb.org/wiki/index.php?title=Drawing_Module)
* Press the little arrow next to the ![icon](http://www.freecadweb.org/wiki/images/thumb/2/27/Drawing_Landscape_A3.png/16px-Drawing_Landscape_A3.png) [New Drawing Page](http://www.freecadweb.org/wiki/index.php?title=Drawing_Landscape_A3) button.
* Select the **A4 Portrait / ISO7200** template. A new tab will open in your FreeCAD window, showing the new page.
* In the tree view (or in the model tab), select the chair model.
* Press the ![icon](http://www.freecadweb.org/wiki/images/thumb/0/03/Drawing_View.png/16px-Drawing_View.png) [Insert view](http://www.freecadweb.org/wiki/index.php?title=Drawing_View) button.
* A View object will be created on our page. Give the view the following properties:
   * X: 100
   * Y: 150
   * Scale: 0.1
   * Rotation: 270
* We now have a nice top view (which is the default projection) of our chair:
 
![the first projection](http://www.freecadweb.org/wiki/images/c/cd/Exercise_drawing_02.jpg)

* Let's repeat the operation twice, to create two more views. We will set their X and Y values, which indicate the position of the view on the page, in order to show them apart from the top view, and their direction, to create different view orientations. Give each new view the following properties:
   * View001 (front view): X: 100, Y: 130, Scale: 0.1, Rotation: 90, Direction: (-1,0,0)
   * View002 (side view): X: 180, Y: 130, Scale: 0.1, Rotation: 90, Direction: (0,-1,0)
 * After that, we obtain the following page:
 
![the three views](http://www.freecadweb.org/wiki/images/7/79/Exercise_drawing_03.jpg)

* We can tweak a bit the aspect of our views if we want, for example we can raise their **Line Width** property to 0.5.

We will now place dimensions and indications on our drawing. There are two ways to add dimensions to a model, one is placing the dimensions inside the 3D model, using the ![icon](http://www.freecadweb.org/wiki/images/thumb/b/b0/Draft_Dimension.png/16px-Draft_Dimension.png) [Dimension](http://www.freecadweb.org/wiki/index.php?title=Draft_Dimension) tool of the [Draft Workbench](http://www.freecadweb.org/wiki/index.php?title=Draft_Module), and then place a view of these dimensions on our sheet with the ![icon](http://www.freecadweb.org/wiki/images/thumb/f/ff/Drawing_DraftView.png/16px-Drawing_DraftView.png) [Draft View](http://www.freecadweb.org/wiki/index.php?title=Drawing_DraftView) tool (which can be used with a single dimension or a group containing dimensions), or we can do things directly on the Drawing sheet, using the [Drawing Dimensioning Workbench](https://github.com/hamish2014/FreeCAD_drawing_dimensioning), which is installable from the [FreeCAD addons](https://github.com/FreeCAD/FreeCAD-addons). We will use here this latter method.

* Switch to the [Drawing Dimensioning Workbench](https://github.com/hamish2014/FreeCAD_drawing_dimensioning)
* Press the **Add Linear Dimension** button. Available nodes are highlighted in green on the drawing page:

![the green nodes](http://www.freecadweb.org/wiki/images/b/b3/Exercise_drawing_04.jpg)

* Click two of these points, then click a third point to place the dimension line:

![the first dimension](http://www.freecadweb.org/wiki/images/b/b7/Exercise_drawing_05.jpg)

* The Linear Dimension tool, as most of the other Drawing Dimensioning tools, will not exit after you finished, allowing you to place more dimensions. When you are done, simply click the **Close** button in the Task panel.
* Repeat the operation, until all the dimensions you wish to indicate are placed. Take a minute to browse through the different options proposed in the Linear Dimension's task panel. For example, by unticking the **auto place text** option, you will be able to place the text of the dimension elsewhere, like on the image below:

![the last dimensions](http://www.freecadweb.org/wiki/images/3/39/Exercise_drawing_06.jpg)

* We will now place two indications, using the **Welding/Groove symbols** tool, selecting the default one (no groove symbol). Draw the two lines like on the image above.
* Now place two texts using the **Add text** tool, and change their **text** property to the contents of your likings.
* Our drawing is now complete, all that is left to do is to fill in the informations of the sheet titleblock. With most of the default FreeCAD templates, this can be done easily, by changing the **Editable Texts** property of the page.

Our page can now be exported to SVG to be worked further in graphical applications like [inkscape](http://www.inkscape.org), or to DXF by selecting menu **File -> Export**. The Drawing Dimensioning workbench also features its own **DXF export** tool, which also supports the annotations added with that workbench. The DXF format is importable in almost all existing 2D CAD applications. Drawing pages can also be directly printed or exported to PDF.

**Downloads**

* The chair model: https://github.com/FreeCAD/FreeCAD-library/blob/master/Furniture/Chairs/IkeaLikeChair.step
* The file created during this exercise: https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/drawing.FCStd
* The SVG sheet produced from that file: https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/drawing.svg

**Read more**

* The Drawing Workbench: http://www.freecadweb.org/wiki/index.php?title=Drawing_Module
* The Drawing Dimensioning Workbench: https://github.com/hamish2014/FreeCAD_drawing_dimensioning
* The FreeCAD library: https://github.com/FreeCAD/FreeCAD-library
* Inkscape: http://www.inkscape.org
