## Generating 2D drawings

When your model cannot be printed or milled directly by a machine, for example it is too big (a building) or it requires manual assembly after the pieces are ready, you will usually need to explain to another person how to do that. In technical fields (engineering, architecture, etc), this is usually done with drawings, that are handed over to the person responsible for assembling the final product, that will explain how to do it.

Typical examples are [Ikea instructions](http://www.ikea.com/ms/en_US/customer_service/assembly_instructions.html), [architectural drawings](https://en.wikipedia.org/wiki/Architectural_drawing) or [blueprints](https://en.wikipedia.org/wiki/Blueprint). These drawings usually contain not only the drawing itself, but also many annotations, such as texts, dimensions, numbers, symbols that will help other people to understand what needs to be done and how.

In FreeCAD, the workbench responsible for making such drawings is the [Drawing Workbench](http://www.freecadweb.org/wiki/index.php?title=Drawing_Module). 

The Drawing Workbench allows you to create sheets, which can be blank or use a pre-made [template](http://www.freecadweb.org/wiki/index.php?title=Drawing_templates) to already have a series of items on the sheet, such as borders and title. On these sheets, you can then place [views](http://www.freecadweb.org/wiki/index.php?title=Drawing_View) of the 3D objects you modeled previously, and configure how these views must appear on the sheet. Finally, thanks to an [addon](https://github.com/FreeCAD/FreeCAD-addons) called [Drawing Dimensioning Workbench](https://github.com/hamish2014/FreeCAD_drawing_dimensioning), you can also place all kinds of annotations on the sheet, such as dimensions, texts, and other usual symbols commonly used in technical drawings.

Drawing sheets, once complete, can be printed or exported as [SVG](https://en.wikipedia.org/wiki/Scalable_Vector_Graphics), PDF or [DXF](https://en.wikipedia.org/wiki/AutoCAD_DXF) files.

In the following exercise, we will show how to build a simple drawing which will convey instructions to build the small wall assembly that we did at the end of the [Modeling for product design](modeling_for_product_design.md) chapter.

**Read more**

* The Drawing Workbench: http://www.freecadweb.org/wiki/index.php?title=Drawing_Module
* The Drawing Dimensioning Workbench: https://github.com/hamish2014/FreeCAD_drawing_dimensioning
