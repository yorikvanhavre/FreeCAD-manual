## Traditional modeling - the CSG way

CSG stands for [Constructive Solid Geometry](https://en.wikipedia.org/wiki/Constructive_solid_geometry) and describes the most basic way to work with solid 3D geometry, which is creating complex objects by adding and removing pieces to/from solids by using Boolean operations such as union, subtraction or intersection.

As we saw earlier in this manual, FreeCAD handles many types of geometry, but the preferred and most useful type, solid, [BREP](https://en.wikipedia.org/wiki/Boundary_representation) geometry, is mainly handled by the [Part Workbench](http://www.freecadweb.org/wiki/index.php?title=Part_Module). Unlike [polygon meshes](https://en.wikipedia.org/wiki/Polygon_mesh), which are made only of points and triangles, BREP objects have their faces defined by mathematical curves, which permit absolute precision, no matter the scale.

![Difference between mesh and brep geometry](http://www.freecadweb.org/wiki/images/1/1a/Mesh_vs_brep.jpg)

The difference between the two can be compared to the difference between bitmap and vector images. As with bitmap images, polygon meshes have their curved surfaces subdivided in a series of points. If you zoom in very closely, or print it very large, you will see, not a curved but a faceted surface. In both vector images and BREP data, the position of any point on a curve is not stored in the geometry but calculated on the fly, with exact precision.

In FreeCAD, all BREP-based geometry is handled by another piece of open-source software, [OpenCasCade](https://en.wikipedia.org/wiki/Open_Cascade_Technology). The main interface between FreeCAD and the OpenCasCade kernel is the Part Workbench. Most other workbenches build their functionality on top of the Part Workbench.

Although other workbenches often offer more advanced tools to build and manipulate geometry, they all actually manipulate Part objects.  It is very useful to know how these objects work internally, and to use the Part tools.  Since, being simpler, they can very often help you to work around problems that the more intelligent tools fail to solve properly.

To illustrate the working of the Part Workbench, we will model this table, using only CSG operations (except the screws, for which we will use one of the addons, and the dimensions, which we will see in the next chapter):

![Complete table](http://www.freecadweb.org/wiki/images/9/99/Exercise_table_complete.jpg)

Let's open FreeCAD and create a new document (**Ctrl+N** or menu File → New),    

The following text assumes some 'default' configurations:
- You will want to be in metric, menu Edit → Preferences → Units Tab → Standard → OK
- The default navigation style; right click on the empty view space follow the Navigation Styles in the list click on CAD  

Switch to the Part Workbench, and begin with the first foot:

* Press the ![icon](http://www.freecadweb.org/wiki/images/thumb/a/a5/Part_Box.png/16px-Part_Box.png) **Cube** button
* Select the cube, (click on Cube in the Model tab, left side) then set the following properties (in the **Data** tab):
   * Length: 80mm (or 8cm, or 0.8m, FreeCAD works in any unit)
   * Width: 80mm
   * Height: 75cm
It is wise to keep an eye on which item is highlighted in the Model tree as it identifies the object being modified.
    * Adjust geometry view with the Fit ![icon](http://www.freecadweb.org/wiki/images/0/0e/Std_ViewFitAll.png) icon
    * Adjust the view with the Axonometric ![icon](http://www.freecadweb.org/wiki/images/a/a2/View-axometric.svg) View icon
* Duplicate the cube (still highlighted in Model tab) by pressing **Ctrl+C** then **Ctrl+V** (or menu Edit → Copy and Paste) (No change will be evident, as the second object is overlaying the first.)
* Select the new object that has been created (Click on Cube001 in the Model tab)
* Change its position by editing its Placement property: (in the Data tab on the left)
(The Placement line will have two cells a Property and a Value Cell.  At the end of the value cell will be 3 dots, select the three dots, they form a button that may not be readily apparent.  The button may need two clicks.  The Task tab should open up and Placement fields become available.) 
   * Position x: 8mm (In the Translation Fields)
   * Position y: 8mm  (Select OK when complete)

You should obtain two overlapping high boxes, one 8mm apart from the other:

![The first objects](http://www.freecadweb.org/wiki/images/d/d4/Exercise_table_01.jpg)

* Now we can subtract one from the other: Select the **first** one, that is, the one that will **stay**, then, with the CTRL key pressed, select the **other** one, that will be **subtracted** (the order is important) and press the ![icon](http://www.freecadweb.org/wiki/images/thumb/4/4a/Part_Cut.png/16px-Part_Cut.png) **Cut** button:
(It is possible to Select either the geometry or the Cubes in the Model Tree)

![First foot complete](http://www.freecadweb.org/wiki/images/0/00/Exercise_table_02.jpg)

Observe that the newly created object, called "Cut", still contains the two cubes we used as operands.  In fact, the two cubes are still there in the document, they have merely been hidden and grouped under the Cut object in the tree.  You can still see and select them by expanding the arrow next to the Cut object, and, if you wish, turn them visible again by right-clicking them or change any of their properties.  (If you click on the grayed out object and duplicate it, you will duplicate hidden objects.  Right clicking on an object will bring up a menu where you can Toggle Visibility.)

Now might be a good time to save the work in a file, menu File →Save As (filename) → Save

* Now let's create the three other feet by duplicating our base cube 6 other times. Since it is still in the clipboard, you can simply paste (Ctrl+V) 6 times. (Don't be afraid, they are overlaying each other and we can edit them separately using their entry in the model tree.)  Change their position as follows:
   * cube002: x: 0, y: 80cm
   * cube003: x: 8mm, y: 79.2cm
   * cube004: x: 120cm, y: 0
   * cube005: x: 119.2cm, y: 8mm
   * cube006: x: 120cm, y: 80cm
   * cube007: x: 119.2cm, y: 79.2cm
   
   (Select Cube00x in Model tree, press three dots at end of Placement line, enter Translation data, press OK.  In graphics window Zoom In/Out using mouse wheel as needed.)

* Now let's do the three other cuts, selecting first the "host" cube then the cube to be cut off. We now have four Cut objects:

![the four feet](http://www.freecadweb.org/wiki/images/4/43/Exercise_table_03.jpg) 

CTRL - S will save the work to this point.

You might be thinking that, instead of duplicating the base cube six times, we could have duplicated the complete foot three times. This is totally true, as always in FreeCAD, there are many ways to achieve a same result. This is a precious thing to remember, because, as we will advance into more complex objects, some operations might not give the correct result and we often need to try other ways.

* We will now make holes for the screws, using the same Cut method. Since we need 8 holes, two in each foot, we could make 8 objects to be subtracted. Instead, let's explore other ways and make 4 tubes, that will be reused by two of the feet. So let's create four tubes by using the ![icon](http://www.freecadweb.org/wiki/images/thumb/d/d4/Part_Cylinder.png/16px-Part_Cylinder.png) **Cylinder** tool. This time let's create the cylinder, translate it, then copy the part feature and translate again. 

If your geometry view is as above, after pressing Cylinder once nothing visibly changed.  A tiny cylinder has overlapped the huge leg.  Move the cursor to the left rear (first) foot near the bottom and mouse wheel to zoom in until you can see the new cylinder.  

Be sure the Cylinder is highlighted in the model tree.  Give the cylinder a radius of 6mm and a length of 130cm.   (Select Cylinder in the model tree and in the Data tab change the Radius and the Height.)  

This time, we will need to rotate the Cylinder, which is also done via the **Placement** property (The Cylinder is still selected in the model tree.  In the Data tab, *Angle property is not what you need,  If you wanted a quarter round, you would set the angle value to 90 degrees*.  At the end of the Placement line select the 3 dots to bring up the Placement fields.)  
 * ***Rotation: Rotation axis with angle*** - - should be set
 Axis: Y; Angle 90 degrees will lay down the cylinder.  Translation: X:-10mm; Y: 40mm; Z: 72cm
 When done select OK

Select the first cylinder and **Ctrl - C** and **Ctrl - V** giving two cylinders overlaying each other.

Select Cylinder001 in the model tree, and open the Placement window by clicking on the three dots at the end of the line.  Change the Translation values: X: -10 mm; Y: 84 cm; Z: 72 cm.  Select OK

In the Model tree select Cylinder001 and copy/paste to overlay another cylinder over the selected cylinder.  Select Cylinder002.  Open the Placement window by selecting the three dots at the end of the Placement line.  Insure ***Rotation: Rotation axis with angle*** is set.
Axis: X; Angle -90  Translation: X: 40mm; Y: -10mm; Z: 70 cm
Select OK to close the Placement window.   Cylinder002 should still be selected in the Model tree, in the Data Tab set the height to 90cm.

Copy Cylinder002 and change the new cylinder's placement values:
Translation: X: 124cm; Y: -10mm; Z: 70cm.
Select OK when finished.

Reviewing the Cylinders:
  * cylinder:       height: 130cm, axis: y, angle: 90°, 
       Translation: x:-10mm, y:40mm, z:72cm
  * cylinder001: height: 130cm, axis: y, angle: 90°, 
       Translation: x:-10mm, y:84cm, z:72cm
  * cylinder002: height: 90cm, angle: 90°, axis: (-1,0,0), 
       Translation: x:40mm, y:-10mm, z:70cm
  * cylinder003: height: 90cm, angle: 90°, axis: (-1,0,0), 
       Translation: x:124cm, y:-10mm, z:70cm

![the cylinders to subtract](http://www.freecadweb.org/wiki/images/3/30/Exercise_table_04.jpg)

You will notice that the cylinders are a bit longer than needed. This is because, as in all solid-based 3D applications, boolean operations in FreeCAD are sometimes oversensitive to face-on-face situations and might fail. By doing this, we put ourselves on the safe side.

* Now let's do the subtractions. Select the first foot, then, with CTRL pressed, select one of the tubes that crosses it, then press the **Cut** button. The hole will be done, and the tube hidden. Find it in the tree view by expanding the pierced foot, it will be needed for the foot at the other end of the tube.  By right clicking on the cylinder in the model tree, it's visibility can be toggled.
* Select another foot pierced by this hidden tube, then repeat the operation, this time pressing the Ctrl key while selecting the tube in the tree view.  Repeat this for the other feet until each of them has its two holes:

![the pierced feet](http://www.freecadweb.org/wiki/images/5/57/Exercise_table_05.jpg)

Now would be a good time to save your work.  A benefit of incremental saving is that if the next step becomes so spoiled you can abandon it with an *Exit without Saving* and restart from a known valid point. 

As you can see, each foot has become a quite long series of operations. All this stays parametric, and you can go change any parameter of any of the older operations anytime. For example if you decide the table should be workbench height, you can go back and change the cube heights to 90cm. In FreeCAD, we often refer to this pile as "modeling history", since it in fact carries all the history of the operations you did. 

Another detail of FreeCAD is the concept of 3D object and 3D operation tends to blend into the same thing. The Cut is at the same time an operation, and the 3D object resulting from this operation. In FreeCAD this is called a "feature", rather than object or operation.

* Now let's do the tabletop, it will be a simple block of wood, let's do it with another **Cube** with length: 126cm, width: 86cm, height: 8cm.   Again it initially will not be visible, as it will come in small, overlaying the bottom of the first foot.  Select the last cube in the Model tree and in the Data tab enter the final dimensions.  Using the 3 dot button at the end of the Position line, enter the Translation  x: 10mm, y: 10mm, z, 67cm.   In the **View** tab, you can give it a nice brownish, wood-like color by changing its **Shape Color** property (insure that the latest Cube is selected in the Model tree, menu View → Appearance . . . → Shape Color (select Button) and choose a color → OK → Close):

![the tabletop](http://www.freecadweb.org/wiki/images/f/f2/Exercise_table_06.jpg)

Another file save would be good.

Notice that, although the legs are 8mm thick, we placed it 10mm away, leaving 2mm between them. This is not necessary, of course, it won't happen with the real table, but it is a common thing to do in that kind of "assembled" models, it helps people who look at the model to understand that these are independent parts, that will need to be attached together manually later.

Now that our five pieces are complete, it is a good time to give them more proper names than "Cut015". By right-clicking the objects in the tree view (or pressing **F2**), you can rename them to something more meaningful to yourself or to another person who would open your file later. It is often said that simply giving descriptive names to your objects is much more important than the way you model them.

Another file save would be good.

* We will now place some screws. There is an extremely useful addon developed by a member of the FreeCAD community, that you can find on the [FreeCAD addons](https://github.com/FreeCAD/FreeCAD-addons) repository, called [Fasteners](https://github.com/shaise/FreeCAD_FastenersWB), that makes the insertion of screws very easy. Installing additional workbenches is easy and described on the addons pages.
* Once you have installed the Fasteners Workbench and restarted FreeCAD, it will appear in the workbenches list, and we can switch to it. Adding a screw to one of our holes is done by first selecting the circular edge of our hole:

![a selected hole](http://www.freecadweb.org/wiki/images/9/99/Exercise_table_07.jpg)

* Then we can press one of the screw icons of the Fasteners Workbench, for example the *EN 1665 Hexagon bolt with flanges, heavy series*.  By moving the mouse to a screw icon and hovering, the name will be revealed.  By clicking on the correct screw icon it will be placed and aligned with our hole, and the diameter will automatically be selected to match the size of our hole. Select each outside hole circle and press the screw icon for each hole

Sometimes the screw will be placed inverted, which we can correct by flipping its **invert** property. (Select the inverted screw, in the Data tab on the Invert line, select in the property cell, from the pull down list ***true***  The picture won't update until pressing ***Enter ***) 

We can also set its offset to 2mm, (in the Data tab) to follow the same rule we used between the tabletop and the feet:

![the placed screw](http://www.freecadweb.org/wiki/images/5/54/Exercise_table_08.jpg)

* Repeat this for all the holes, save the file and our table is complete!

By now frequent incremental file saves should become second nature.

**The internal structure of Part objects**

As we saw above, it is possible in FreeCAD to select not only whole objects, but parts for them, such as the circular border of our screw hole. This is a good time to have a quick look at how Part objects are constructed internally. Every workbench that produces Part geometry will be based on these:

* **Vertices**: These are points (usually endpoints) on which all the rest is built. For example, a line has two vertices.
* **Edges**: the edges are linear geometry like lines, arcs, ellipses or [NURBS](https://en.wikipedia.org/wiki/Non-uniform_rational_B-spline) curves. They usually have two vertices, but some special cases have only one (a closed circle for example).
* **Wires**: A wire is a sequence of edges connected by their endpoints. It can contain edges of any type, and it can be closed or not.
* **Faces**: Faces can be planar or curved, and can be formed by one closed wire, which forms the border of the face, or more than one, in case the face has holes.
* **Shells**: Shells are simply a group of faces connected by their edges. It can be open or closed.
* **Solids**: When a shell is tightly closed, that is, it does not "leak", it becomes a solid. Solids carry the notion of inside and outside. Many workbench rely on this to make sure the objects they produce can be built in the real world.
* **Compounds**: Compounds are simply aggregates of other shapes, no matter their type, into a single shape.

In the 3D view, you can select individual **vertices**, **edges** or **faces**. Selecting one of these also selects the whole object.

**A note about shared design**

You might look at the table above, and think its design is not good. The attachment of the feet to the tabletop is probably too weak. You might want to add reinforcing pieces, or you have other ideas to make it better. This is where sharing becomes interesting. You can download the file made during this exercise from the link below, and modify it to make it better. Then, if you share that improved file, others might be able to make it even better, or use your well-designed table in their projects. Your design might then give other ideas to other people, and maybe you will have helped a tiny bit to make a better world...

**Downloads**

* The file produced in this exercise: https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/table.FCStd

**Read more**

* The Part Workbench: http://www.freecadweb.org/wiki/index.php?title=Part_Module
* The FreeCAD addons repository: https://github.com/FreeCAD/FreeCAD-addons
* The Fasteners Workbench: https://github.com/shaise/FreeCAD_FastenersWB
