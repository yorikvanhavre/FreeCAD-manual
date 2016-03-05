## BIM modeling

BIM stands for [Building Information Modeling](https://en.wikipedia.org/wiki/Building_information_modeling). The exact definition of what it is varies, but we can say simply that is how buildings and other large structures like bridges, tunnels, etc... are modeled today. BIM models are usually based on 3D models, and also include a series of additional layers of information, such as materials information, relationships to other objects or models, or special instructions for building or maintenance. This extra information permits all kinds of advanced analyses of the model, such as structural resistance, cost and construction time estimations, or calculaitons of energy consumption.

The [Arch Workbench](http://www.freecadweb.org/wiki/index.php?title=Arch_Module) of FreeCAD implements a series of tools and facilities for BIM modeling. Although it has a different purpose, it is made to work in tight integration with the rest of FreeCAD: Anything made with any other workbench of FreeCAD can become an Arch object, or be used as a base for an Arch object.

As in the [PartDesign Workbench](http://www.freecadweb.org/wiki/index.php?title=PartDesign_Workbench), the objects produced by the Arch Workbench are meant to be built in the real world. Therefore, they need to be **solid**. The Arch tools usually take care of that automatically, and also provide utility tools to help you check the validity of objects.

The Arch Workbench also includes all the tools from the [Draft Workbench](http://www.freecadweb.org/wiki/index.php?title=Draft_Module), and uses its grid and snapping system. Before beginning, it is always a good idea to browse through the preferences pages of both Draft and Arch and set the default settings to your likings.

In this chapter, we will see how to model this small building:

![the arch model](http://www.freecadweb.org/wiki/images/c/cb/Exercise_arch_01.jpg)

and produce a plan and a section view from it:

![the drawing page](http://www.freecadweb.org/wiki/images/1/15/Exercise_arch_02.jpg)

* Create a new document, and switch to the [Arch Workbench](http://www.freecadweb.org/wiki/index.php?title=Arch_Module).
* Open menu **Edit -> Preferences -> Draft -> Grid and Snapping** and set the **grid spacing** setting to 1000mm, so we have a one meter-based grid, which will be convenient for the size of our buiding.
* On the **snapping toolbar**, make sure the ![icon](http://www.freecadweb.org/wiki/images/thumb/f/f5/Snap_Grid.png/16px-Snap_Grid.png) [grid snap](http://www.freecadweb.org/wiki/index.php?title=Draft_ToggleGrid) button is enabled, so we can use the grid  as much as possible.
* Set the [Working Plane](http://www.freecadweb.org/wiki/index.php?title=Draft_SelectPlane) to **XY** plane
* Draw four lines with the ![icon](http://www.freecadweb.org/wiki/images/thumb/a/a8/Draft_Line.png/16px-Draft_Line.png) [Draft Line](http://www.freecadweb.org/wiki/index.php?title=Draft_Line) tool. You can enter coordinates manually, or simply pick the points on the grid with the mouse:
   * From point (0,0) to point (0,3)
   * From point (0,3) to point (4,3)
   * From point (4,3) to point (4,0)
   * From point (4,0) to point (0,0)

![the 4 lines](http://www.freecadweb.org/wiki/images/1/15/Exercise_arch_03.jpg)

Notice that we drew always in the same direction (clockwise). This is not necessary, but will ensure that the walls that we will build next all have the same left and right directions. You might also think we could simply have drawn a rectangle here, which is true. But the four lines will allow us to illustrate better how to add one object into another.

* Select the first line, then press the ![icon](http://www.freecadweb.org/wiki/images/thumb/a/a5/Arch_Wall.png/16px-Arch_Wall.png) [Arch Wall](http://www.freecadweb.org/wiki/index.php?title=Arch_Wall) button.
* Repeat this for the 3 other lines, untilyou have 4 walls.
* Select the four walls, and set their **Height** property to **3.00m** and their **Alignment** property to **left**. If you didn't draw the lines in the same order as we did above, some of the walls might have their left and right directions flipped, and might need to be set to **right** instead. You will obtain four intersecting walls, on the inside of the baselines:

![the 4 walls](http://www.freecadweb.org/wiki/images/e/e0/Exercise_arch_04.jpg)

Now we need to join these walls together, so they intersect properly. This is not necessary when your walls are drawn in a way that they already connect cleanly, but here we need to, since they are intersecting. In Arch, this is done by electing one of the walls to be the "host", and adding the others to it, as "additions". All arch objects can have any number of additions (objects whose geometry will be added to the host's geometry), and subtractions (objects whose geometry will be subtracted). The additions and subtractions of an object can be managed anytime by double-clicking the object in the tree.
* Select the four walls with **Ctrl** pressed, the last one being the wall that you chose to become the host
* Press the ![icon](http://www.freecadweb.org/wiki/images/thumb/d/d2/Arch_Add.png/16px-Arch_Add.png) [Arch Add](http://www.freecadweb.org/wiki/index.php?title=Arch_Add) button. The four walls have now been turned into one:

![the final wall](http://www.freecadweb.org/wiki/images/7/7b/Exercise_arch_05.jpg)

The individual walls are however still accessible, by expanding the wall in the tree view.

* Let's now place a door. In FreeCAD, doors are considered a special case of windows, so this is done using the [Window](http://www.freecadweb.org/wiki/index.php?title=Arch_Window) tool.
* Start by selecting the wall. This is not necessary, but a good habit to take. If an object is selected when starting the window tool, you will force the window to be inserted in that object, even if you snap to another object.
* Set the [Working Plane](http://www.freecadweb.org/wiki/index.php?title=Draft_SelectPlane) to **auto** so we are not restricted to the ground plane
* Press the ![icon](http://www.freecadweb.org/wiki/images/thumb/a/a4/Arch_Window.png/16px-Arch_Window.png) [Window](http://www.freecadweb.org/wiki/index.php?title=Arch_Window) button.
* In the window creation panel, select the **Simple door** preset, and set its **Width** to 0.9m and its **Height** to 2.1m
* Make sure the ![icon](http://www.freecadweb.org/wiki/images/thumb/f/f7/Snap_Near.png/16px-Snap_Near.png) [Near snap](http://www.freecadweb.org/wiki/index.php?title=Draft_Near) location is turned on, so we can snap on faces
* Place your window roughly on the middle of the front face of the wall:

![Positioning the door](http://www.freecadweb.org/wiki/images/5/5f/Exercise_arch_06.jpg)

* After clicking, our window is placed on the correct face, but not exactly where we want:

![the placed door](http://www.freecadweb.org/wiki/images/8/87/Exercise_arch_07.jpg)

* We can now set the precise location by expanding the wall and the window objects in the tree view, and changing the **Placement** property of the base sketch of our door. Set its position to **x = 2m, y = 0, z = 0**. Our window is now exactly where we want it:

![the final door](http://www.freecadweb.org/wiki/images/a/ab/Exercise_arch_08.jpg)

* Repeat the operation to place a window: Select the wall, press the window tool, select the **Open 2-pane** preset, and place a 1m x 1m window in the same face as the door. Set the placement of the underlying sketch to position **x = 0.6m, y = 0, z = 1.1m**, so the upper line of the window is aligned to the top of the door.

![the window](http://www.freecadweb.org/wiki/images/c/c9/Exercise_arch_09.jpg)

Windows are always built on sketches. It is easy to create custom windows by first creating a sketch on a face, then turning it into a window by selecting it, then pressing the window button. Then, the window creation parameters, that is, which wires of the sketch must be extruded and how much, can be defined by double-clickingthe window in the tree view. Let's now create a slab:

* Set the [Working Plane](http://www.freecadweb.org/wiki/index.php?title=Draft_SelectPlane) to **XY** plane
* Create a ![icon](http://www.freecadweb.org/wiki/images/thumb/1/14/Draft_Rectangle.png/16px-Draft_Rectangle.png) [rectangle](http://www.freecadweb.org/wiki/index.php?title=Draft_Rectangle) with a **length** of 5m, a height of **4m**, and place it at position x:-0.5m, y:-0.5m, z:0.
* Select the rectangle
* Click the ![icon](http://www.freecadweb.org/wiki/images/thumb/3/35/Arch_Structure.png/16px-Arch_Structure.png) [structure](http://www.freecadweb.org/wiki/index.php?title=Arch_Structure) tool to create a slab from the rectangle
* Set the **height** property of the slab to 0.2m and its **normal** direction to (0,0,-1) because we want it to extrude downwards. We could also simply have moved it 0.2m down, but it is always good practice to keep extruded objects at the same place as their base profile.
* Set the **Role** property of the slab to **slab**. This is not necessary in FreeCAD, but is important for IFC export, as it will ensure that the object is exported with the correct IFC type.

![the base slab](http://www.freecadweb.org/wiki/images/5/5b/Exercise_arch_10.jpg)

* Let's now use one of the structural presets to make a metallic beam. Click the ![icon](http://www.freecadweb.org/wiki/images/thumb/3/35/Arch_Structure.png/16px-Arch_Structure.png) [structure](http://www.freecadweb.org/wiki/index.php?title=Arch_Structure) button, select a **HEB 180** preset, and set its height to **4m**. Place it anywhere:

![a metallic element](http://www.freecadweb.org/wiki/images/9/9d/Exercise_arch_11.jpg)

* Adjust its **placement** by setting its **rotation** to 90° in the (1,0,0) axis, and its **position** to x:90mm, y:3.5m, z:3.09m. This will position the beam exactly on one of the side walls:

![the positioned beam](http://www.freecadweb.org/wiki/images/f/f7/Exercise_arch_12.jpg)

* We need now to duplicate this beam a couple of times. We could do that one by one using the ![icon](http://www.freecadweb.org/wiki/images/thumb/3/39/Draft_Clone.png/16px-Draft_Clone.png) [clone](http://www.freecadweb.org/wiki/index.php?title=Draft_Clone) tool, but there is a better way, to do all the copies at once using an array:
* Select the beam
* Press the ![icon](http://www.freecadweb.org/wiki/images/thumb/c/c8/Draft_Array.png/16px-Draft_Array.png) [Array](http://www.freecadweb.org/wiki/index.php?title=Draft_Array) button
* Set the **Number X** property of the array to 6, leave the Y and Z numbers to 1
* Expand the **interval X** property, and press the small  ![icon](http://www.freecadweb.org/wiki/images/thumb/3/38/Bound-expression-unset.png/16px-Bound-expression-unset.png) **expression** icon at the right side of the X field. This will open an [expressions editor](http://www.freecadweb.org/wiki/index.php?title=Expressions) (depending on your operating system, the editor can be located somewhere else than on the image below, such as in the upper left corner of your screen).
* Write **(4m-180mm)/5** in the expression field, and press **OK**. This will set the x value to 0.764 (4m is the total length of our front wall, 180mm is the width of the beam, which is why it is called HEB180):

![the expression engine](http://www.freecadweb.org/wiki/images/7/74/Exercise_arch_13.jpg)

**Downloads**

* The file produced during this exercise: https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/house.FCStd

**Read more**

* The Arch Workbench: http://www.freecadweb.org/wiki/index.php?title=Arch_Module
* The Draft working plane: http://www.freecadweb.org/wiki/index.php?title=Draft_SelectPlane
* The Draft snapping settings: http://www.freecadweb.org/wiki/index.php?title=Draft_Snap
* The expressions system: http://www.freecadweb.org/wiki/index.php?title=Expressions
