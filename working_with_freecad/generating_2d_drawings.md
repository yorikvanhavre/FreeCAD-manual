## Generating 2D drawings

When your model cannot be printed or milled directly by a machine, for example it is too big (a building) or it requires manual assembly after the pieces are ready, you will usually need to explain to another person how things fit together. In technical fields (engineering, architecture, etc), this is usually done with drawings, that are handed over to someone else explaining the designer's vision.

Typical examples are [Ikea instructions](http://www.ikea.com/ms/en_US/customer_service/assembly_instructions.html), [architectural drawings](https://en.wikipedia.org/wiki/Architectural_drawing) or [blueprints](https://en.wikipedia.org/wiki/Blueprint). These drawings usually contain not only the drawing itself, but also many annotations, such as texts, dimensions, numbers, symbols that will help others to understand what needs to be done and how.

In FreeCAD, the workbench responsible for making such drawings is the [Drawing Workbench](http://www.freecadweb.org/wiki/index.php?title=Drawing_Module). 

The Drawing Workbench allows you to create sheets, which can be blank or use a pre-made [template](http://www.freecadweb.org/wiki/index.php?title=Drawing_templates) containing pre-drawn items on the sheet, such as borders and title block. On these sheets, you can then place [views](http://www.freecadweb.org/wiki/index.php?title=Drawing_View) of the 3D objects you modeled previously, and configure how these views must appear on the sheet. Finally, thanks to an [addon](https://github.com/FreeCAD/FreeCAD-addons) called [Drawing Dimensioning Workbench](https://github.com/hamish2014/FreeCAD_drawing_dimensioning), you can also place all kinds of annotations on the sheet, such as dimensions, texts, and other usual symbols commonly used in technical drawings.

Drawing sheets, once complete, can be printed or exported as [SVG](https://en.wikipedia.org/wiki/Scalable_Vector_Graphics), PDF or [DXF](https://en.wikipedia.org/wiki/AutoCAD_DXF) files.

In the following exercise, we will see how to create a simple drawing of a chair model found in the [FreeCAD library](https://github.com/FreeCAD/FreeCAD-library) (Furniture -> Chairs -> IkeaChair). The FreeCAD library can easily be added to your FreeCAD installation (refer to the [installing](../discovering_freecad/installing.md#installing-additional-content) chapter of this manual), or you can simply download the model from the library webpage, or via the direct link provided at the end of this chapter.

![the drawing exercise](http://www.freecadweb.org/wiki/images/4/40/Exercise_drawing_01.jpg)

* Load the IkeaChair file from the library. You can choose between the .FCStd version, which will load the full modeling history, or the .step version, which will create only one object, without the history. Since we won't need to model any further now, it is best to choose the .step version, as it will be easier to manipulate.

![the Parts library](http://www.freecadweb.org/wiki/images/6/69/Parts_library.jpg)

* Switch to the [Drawing Workbench](http://www.freecadweb.org/wiki/index.php?title=Drawing_Module)
* Press the small arrow next to the ![icon](http://www.freecadweb.org/wiki/images/thumb/2/27/Drawing_Landscape_A3.png/16px-Drawing_Landscape_A3.png) [New Drawing Page](http://www.freecadweb.org/wiki/index.php?title=Drawing_Landscape_A3) button.
* Select the **A4 Portrait / ISO7200** template. A new tab will open in your FreeCAD window, showing the new page.
* In the tree view (or in the model tab), select the chair model.  Select the whole model, both the seat and the frame.
* Press the ![icon](http://www.freecadweb.org/wiki/images/thumb/0/03/Drawing_View.png/16px-Drawing_View.png) [Insert view](http://www.freecadweb.org/wiki/index.php?title=Drawing_View) button.
* A View object will be created on our page. Highlight both View lines in the Model tree, and click on the Data tab.  Give the view the following properties:
   * X: 100
   * Y: 150
   * Scale: 0.1
   * Rotation: 270
* We now have a nice top view (which is the default projection) of our chair:
 
![the first projection](http://www.freecadweb.org/wiki/images/c/cd/Exercise_drawing_02.jpg)

* Let's repeat the operation twice, to create two more views. Remember to highlight both items in the Model tree before pressing **Insert View**.  We will set their X and Y values, which indicate the position of the view on the page, in order to show them apart from the top view, and their direction, to create different view orientations. (Again highlight both Views to change both at the same time.) Give each new view the following properties:
   * View002 & 003 (front view): X: 100, Y: 130, Scale: 0.1, Rotation: 90, Direction: (-1,0,0) (click on small arrow to the left of Direction to access values.)
   * View004 & 005 (side view): X: 180, Y: 130, Scale: 0.1, Rotation: 90, Direction: (0,-1,0)
 * After that, we obtain the following page (for some it will seem unnatural for the top view to appear beneath the front view like this):
 
![the three views](http://www.freecadweb.org/wiki/images/7/79/Exercise_drawing_03.jpg)

* We can tweak a bit the aspect of our views if we want, for example we can raise their **Line Width** property to 0.5. (In the Model tree, click on the first View and Shift click on the last View to highlight all of them, Data tab, Line Width property, set to 0.5)
* Now would be a good time for an incremental save.

We will now place dimensions and indications on our drawing. There are two ways to add dimensions to a model, one is placing the dimensions inside the 3D model, using the ![icon](http://www.freecadweb.org/wiki/images/thumb/b/b0/Draft_Dimension.png/16px-Draft_Dimension.png) [Dimension](http://www.freecadweb.org/wiki/index.php?title=Draft_Dimension) tool of the [Draft Workbench](http://www.freecadweb.org/wiki/index.php?title=Draft_Module), and then place a view of these dimensions on our sheet with the ![icon](http://www.freecadweb.org/wiki/images/thumb/f/ff/Drawing_DraftView.png/16px-Drawing_DraftView.png) [Draft View](http://www.freecadweb.org/wiki/index.php?title=Drawing_DraftView) tool (which can be used with a single dimension or a group containing dimensions), or we can do things directly on the Drawing sheet, using the [Drawing Dimensioning Workbench](https://github.com/hamish2014/FreeCAD_drawing_dimensioning), which is available from the [FreeCAD addons](https://github.com/FreeCAD/FreeCAD-addons). We will use this latter method, remembering that dimensions will not update should the model be modified.

* Switch to the [Drawing Dimensioning Workbench](https://github.com/hamish2014/FreeCAD_drawing_dimensioning)
* Press the **Add Linear Dimension** button. Available nodes are highlighted in green on the drawing page:

![the green nodes](http://www.freecadweb.org/wiki/images/b/b3/Exercise_drawing_04.jpg)

* Click two of these points, then click a third point to place the dimension line (the mouse scroll wheel will allow zooming in or out as needed):

![the first dimension](http://www.freecadweb.org/wiki/images/b/b7/Exercise_drawing_05.jpg)

* The Linear Dimension tool, as most of the other Drawing Dimensioning tools, will not exit after completing a dimension, allowing you to place more dimensions. When you are done, simply click the **Close** button in the Task panel.
* Repeat the operation, until all the dimensions you wish to add are placed. Take a minute to browse through the different options proposed in the Linear Dimension's task panel. The task panel changes will apply to the next dimension added.  For example, by unticking the **auto place text** option, you will be able to place the text of the dimension elsewhere, using a fourth click, like on the image below:

![the last dimensions](http://www.freecadweb.org/wiki/images/3/39/Exercise_drawing_06.jpg)

* Let us place two **grab points** in the middle of the areas shown by the arrow tips above.  We will now place two leaders, using the **Welding/Groove symbols** tool, selecting the default one (no groove symbol). Draw the two lines like on the image above.
* Now place two texts using the **Add text** tool, and change their **text** property to your liking.  (Highlight the Text line in the Model tree and in the Data tab, the text property value change to the desired verbiage.)
* Our drawing is now complete, all that is left to do is to enter information into the sheet title block. With most of the default FreeCAD templates, this can be done easily, by changing the **Editable Texts** property of the page. (Highlight the Page line of the Model tree, Data tab, Editable Texts Property, mouse click on the three periods at the end of the value cell. It may take more than one mouse click on the periods.  In the window that pops up, paint the desired text, type new text in its place, making all the desired line changes. Click OK when done.)

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
