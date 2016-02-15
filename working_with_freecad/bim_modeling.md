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
* Press the ![icon](http://www.freecadweb.org/wiki/images/thumb/d/d2/Arch_Add.png/16px-Arch_Add.png) [Arch Add](http://www.freecadweb.org/wiki/index.php?title=Arch_Add) button. The four walls have now be turned into one:

![the final wall](http://www.freecadweb.org/wiki/images/7/7b/Exercise_arch_05.jpg)

**Downloads**

* The file produced during this exercise: https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/house.FCStd

**Read more**

* The Arch Workbench: http://www.freecadweb.org/wiki/index.php?title=Arch_Module
* The Draft working plane: http://www.freecadweb.org/wiki/index.php?title=Draft_SelectPlane
* The Draft snapping settings: http://www.freecadweb.org/wiki/index.php?title=Draft_Snap
