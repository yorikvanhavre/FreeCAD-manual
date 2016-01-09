## Preparing models for 3D printing

One of the main uses of FreeCAD is to produce real-world objects. These can be designed in FreeCAD, and then made real by different ways, such as communicated to other people who will then build them, or, more and more fequently, sent directly to a [3D printer](https://en.wikipedia.org/wiki/3D_printing) or a [CNC mill](https://en.wikipedia.org/wiki/Milling_%28machining%29). This chapter will show you how to get your models ready to send to these machines.

If you have been cautious while modeling, most of the difficulty you might encounter when printing your model in 3D has already been avoided. This involves basically:

* Making sure that your 3D objects are **solid**. Real-world objects are solid, the 3D model must be solid too. We saw in earlier chapters that FreeCAD helps you a lot in that regard, and that the [Part Design Workbench](http://www.freecadweb.org/wiki/index.php?title=PartDesign_Workbench) will notify you if you do an operation that prevents your model to stay solid. The [Part Workbench](http://www.freecadweb.org/wiki/index.php?title=Part_Module) also contains a ![icon](http://www.freecadweb.org/wiki/images/thumb/5/5f/Part_CheckGeometry.png/16px-Part_CheckGeometry.png) [Check Geometry](http://www.freecadweb.org/wiki/index.php?title=Part_CheckGeometry) tool that is handy to check further for possible defects.
* Making sure about the **dimensions** of your objects. One millimeter will be one millimeter in real-life. Every dimension matters. 
* Controlling the **degradation**. No 3D printing or CNC milling system can take FreeCAD files directly. Most of them will only understand a machine language called [G-Code](https://en.wikipedia.org/wiki/G-code). G-code has dozens of different dialects, each machine or vendor usually using its own. The conversiom of your models into G-Code can be easy and automatic, but you can also do it manually, with total control over the output. In any case, some loss of quality of your model will unavoidably occur during the process. When printing in 3D, you must always make sure this loss of quality stays below your minimal requirements.

Below, we will assume that the first two criterias are met, and that by now you are able to produce solid objects with correct dimensions. We will now see how to address the third point.

### Exporting to external slicers

This is the technique most commonly used for 3D printing. The 3D object is exported to another program (the slicer) which will generate the G-code from the object, by slicing it into thin layers (hence the name), which will reproduce the movements that the 3D printer will do. Since many of those printers are home-built, there are often small differences from one to the other. These programs usually offer advanced configuration possibilities that allow to tailor the output exactly for the particularities of your 3D printer.

Actual 3D printing, however, is a too vast subject for this manual. But we will see how to export and use these slicers to check that the output is correct.

#### Converting objects to meshes

None of the slicers will, at this date, take directly solid geometry as we produce in FreeCAD. So we will need to convert any object we want to 3D print into a [mesh](https://en.wikipedia.org/wiki/Polygon_mesh) firs, that the slicer can use. Fortunately, as much as converting a mesh to a solid is a complicated operation, the contrary, converting a solid to a mesh, is very straightforward. All we need to be careful about, is that it is now that the degradation we mentioned above will occur. We need to check that the degradation stays inside acceptable limits.

All the mesh handling, in FreeCAD, is done by another specific workbench, the [Mesh Workbench](http://www.freecadweb.org/wiki/index.php?title=Mesh_Module). This workbench contains, apart from the most important, the tools that convert between Part and Mesh objects, several utilities meant to analyze and repair meshes. Although working with meshes is not the focus of FreeCAD, when working with 3D modeling, you often need to deal with mesh objects, since their use is very widespread among other applications. This workbench allows you to handle them fully in FreeCAD.

* Let's convert one of the objects we modelled in the previous chapters, such as the lego piece (which can be downloaded from the end of the previous chapter).
* Open the FreeCAD file containing the lego piece.
* Switch to the [Mesh Workbench](http://www.freecadweb.org/wiki/index.php?title=Mesh_Module)
* Select the lego brick
* Select menu **Meshes -> Create Mesh from Shape**
* A task panel will open with several options. Some additional meshing algorithms (Mefisto or Netgen) might not be available, depending on how your version of FreeCAD was compiled. The Standard meshing algorithm will always be present. It offers less possibilities than the two others, but is totally sufficient for small objects that fit into the maximum print size of a 3D printer.

![the meshing options](http://www.freecadweb.org/wiki/images/d/de/Exercise_meshing_01.jpg)

* Select the **Standard** mesher, and leave the deviation value to the default value of **0.10**. Press **Ok**.
* A mesh object will be created, exactly on top of our solid object. Either hide the solid, or move one of the objects apart, so you can compare both.
* Change the **View -> Display Mode** of the new mesh object to **Flat Lines**, in order to see how the triangulation occured.
* If yuo are not happy, and think that the result is too coarse, you can repeat the operation, lowering the deviation value. In the example below, the left mesh used the default value of **0.10**, while the right one uses **0.01**:

![meshing differences](http://www.freecadweb.org/wiki/images/b/b2/Exercise_meshing_02.jpg)

In most cases, though, the default values will give a satisfying result.

* We can now export our mesh to a mesh format, such as [STL](https://en.wikipedia.org/wiki/STL_%28file_format%29), which is the most widely used format in 3D printing, by using menu **File -> Export** and choosing the STL file format.

#### Using Slic3r

#### Using the Cura addon

![3d-printed lego](http://www.freecadweb.org/wiki/images/5/54/3d_printed_lego.jpg)

### Generating G-code

**Read more**

* The Mesh Workbench: http://www.freecadweb.org/wiki/index.php?title=Mesh_Module
* The STL file format: https://en.wikipedia.org/wiki/STL_%28file_format%29


