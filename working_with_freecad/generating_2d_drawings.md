## Generating 2D drawings

When your model cannot be printed or milled directly by a machine, for example it is too big (a building) or it requires manual assembly after the pieces are ready, you will usually need to explain to another person how to do that. In technical fields (engineering, architecture, etc), this is usually done with drawings, that are handed over to the person responsible for assembling the final product, that will explain how to do it.

Typical examples are [Ikea instructions](http://www.ikea.com/ms/en_US/customer_service/assembly_instructions.html), [architectural drawings](https://en.wikipedia.org/wiki/Architectural_drawing) or [blueprints](https://en.wikipedia.org/wiki/Blueprint). These drawings usually contain not only the drawing itself, but also many annotations, such as texts, dimensions, numbers, symbols that will help other people to understand what needs to be done and how.

In FreeCAD, the workbench responsible for making such drawings is the [Drawing Workbench](http://www.freecadweb.org/wiki/index.php?title=Drawing_Module). 

The Drawing Workbench allows you to create sheets, which can be blank or use a pre-made [template](http://www.freecadweb.org/wiki/index.php?title=Drawing_templates) to already have a series of items on the sheet, such as borders and title. On these sheets, you can then place [views](http://www.freecadweb.org/wiki/index.php?title=Drawing_View) of the 3D objects you modeled previously, and configure how these views must appear on the sheet. Finally, thanks to an [addon](https://github.com/FreeCAD/FreeCAD-addons) called [Drawing Dimensioning Workbench](https://github.com/hamish2014/FreeCAD_drawing_dimensioning), you can also place all kinds of annotations on the sheet, such as dimensions, texts, and other usual symbols commonly used in technical drawings.

Drawing sheets, once complete, can be printed or exported as [SVG](https://en.wikipedia.org/wiki/Scalable_Vector_Graphics), PDF or [DXF](https://en.wikipedia.org/wiki/AutoCAD_DXF) files.

In the following exercise, we will see how to create a simple drawing which will teach children (and grown-ups too, why not) to build the small Lego wall assembly that we did at the end of the [Modeling for product design](modeling_for_product_design.md) chapter:

![the drawing exercise](http://www.freecadweb.org/wiki/images/4/40/Exercise_drawing_01.jpg)

Before starting to build the Drawing sheet, we will make a small preparation. When placing objects on the Drawing page, the lines of that object that you don't see will be hidden. However, this happens individually for each object. If we want one object to hide another, like the two first blocks on the image above, they must become one object. This is done with the [Make Compound](http://www.freecadweb.org/wiki/index.php?title=Part_MakeCompound) tool found in the [Part Workbench](http://www.freecadweb.org/wiki/index.php?title=Part_Module):

* Select one of the base block, and, with **Ctrl** pressed, the second base block.
* Switch to the [Part Workbench](http://www.freecadweb.org/wiki/index.php?title=Part_Module)
* Select menu **Part -> [Make Compound](http://www.freecadweb.org/wiki/index.php?title=Part_MakeCompound)**
 
A compound object will be created, that is made of our two base blocks. In the example above, notice that I moved a little bit one of the blocks inside the compound to make the drawing clearer. Now we are ready to build the sheet:

* Load the file containing the assembly we made at the end of the [Modeling for product design](modeling_for_product_design.md) chapter (or use the file linked at the end of this chapter, which also contains the assembly).
* Switch to the [Drawing Workbench](http://www.freecadweb.org/wiki/index.php?title=Drawing_Module)
* Press the little arrow next to the ![icon](http://www.freecadweb.org/wiki/images/thumb/2/27/Drawing_Landscape_A3.png/16px-Drawing_Landscape_A3.png) [New Drawing Page](http://www.freecadweb.org/wiki/index.php?title=Drawing_Landscape_A3) button.
* Select the **A4 Portrait / ISO7200** template. A new tab will open in your FreeCAD window, showing the new page.
* In the tree view (or in the model tab), select the compound.
* Press the ![icon](http://www.freecadweb.org/wiki/images/thumb/0/03/Drawing_View.png/16px-Drawing_View.png) [Insert view](http://www.freecadweb.org/wiki/index.php?title=Drawing_View) button.
* A View object will be created on our page. Give the view the following properties:
   * X: 123
   * Y: 172
   * Scale: 1.5
   * Rotation: 60
   * Direction: X: 1, Y: -1, Z:1
 * We have given an isometric projection to our view (the (1,-1,1) direction), and now we have a nice isometric view of our compound:
 
![the first projection](http://www.freecadweb.org/wiki/images/c/cd/Exercise_drawing_02.jpg)

* Let's repeat the operation with the two remaining blocks. We will set their X and Y values, which indicate the position of the view on the page, in order to show them apart from their "mounted" location, like on the image above. Give each view the following properties:
   * View of block 03: X: 125.5, Y: 127, Scale: 1.5, Rotation: 60, Direction: (1,-1,1)
   * View of block 04: X: 123, Y: 94, Scale: 1.5, Rotation: 60, Direction: (1,-1,1)
 * After that, we obtain the following page:
 
![the four blocks projected](http://www.freecadweb.org/wiki/images/7/79/Exercise_drawing_03.jpg)

**Downloads**

* The file created during this exercise: https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/drawing.FCStd
* The SVG sheet produced from that file: https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/legowall.svg

**Read more**

* The Drawing Workbench: http://www.freecadweb.org/wiki/index.php?title=Drawing_Module
* The Drawing Dimensioning Workbench: https://github.com/hamish2014/FreeCAD_drawing_dimensioning
