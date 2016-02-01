## Generating 2D drawings

When your model cannot be printed or milled directly by a machine, for example it is too big (a building) or it requires manual assembly after the pieces are ready, you will usually need to explain to another person how to do that. In technical fields (engineering, architecture, etc), this is usually done with drawings, that are handed over to the person responsible for assembling the final product, that will explain how to do it.

Typical examples are [Ikea instructions](http://www.ikea.com/ms/en_US/customer_service/assembly_instructions.html), [architectural drawings](https://en.wikipedia.org/wiki/Architectural_drawing) or [blueprints](https://en.wikipedia.org/wiki/Blueprint). These drawings usually contain not only the drawing itself, but also many annotations, such as texts, dimensions, numbers, symbols that will help other people to understand what needs to be done and how.

In FreeCAD, the workbench responsible for making such drawings is the [Drawing Workbench](http://www.freecadweb.org/wiki/index.php?title=Drawing_Module). 

The Drawing Workbench allows you to create sheets, which can be blank or use a pre-made [template](http://www.freecadweb.org/wiki/index.php?title=Drawing_templates) to already have a series of items on the sheet, such as borders and title. On these sheets, you can then place [views](http://www.freecadweb.org/wiki/index.php?title=Drawing_View) of the 3D objects you modeled previously, and configure how these views must appear on the sheet. Finally, thanks to an [addon](https://github.com/FreeCAD/FreeCAD-addons) called [Drawing Dimensioning Workbench](https://github.com/hamish2014/FreeCAD_drawing_dimensioning), you can also place all kinds of annotations on the sheet, such as dimensions, texts, and other usual symbols commonly used in technical drawings.

Drawing sheets, once complete, can be printed or exported as [SVG](https://en.wikipedia.org/wiki/Scalable_Vector_Graphics), PDF or [DXF](https://en.wikipedia.org/wiki/AutoCAD_DXF) files.

In the following exercise, we will see how to create a simple drawing of a chair model found in the [FreeCAD library](https://github.com/FreeCAD/FreeCAD-library) (Furniture -> Chairs -> IkeaChair). The FreeCAD library can easily be added to your FreeCAD installation (refer to the [installing](discovering_freecad/installing) chapter of this manual), or you can simply download the model from the library webpage, or via the direct link provided at the bottom of this chapter.

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

* We can tweak a bit the aspect of our views if we want, for example we can set their **Line Width** property to 0.5.

**Downloads**

* The chair model: https://github.com/FreeCAD/FreeCAD-library/blob/master/Furniture/Chairs/IkeaLikeChair.step
* The file created during this exercise: https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/drawing.FCStd
* The SVG sheet produced from that file: https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/drawing.svg

**Read more**

* The Drawing Workbench: http://www.freecadweb.org/wiki/index.php?title=Drawing_Module
* The Drawing Dimensioning Workbench: https://github.com/hamish2014/FreeCAD_drawing_dimensioning
* The FreeCAD library: https://github.com/FreeCAD/FreeCAD-library
