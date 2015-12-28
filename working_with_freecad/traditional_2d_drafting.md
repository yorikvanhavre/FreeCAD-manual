## Traditional 2D drafting

You might be interested by FreeCAD because you already have some technical drawing experience, for example with software like [AutoCAD](https://en.wikipedia.org/wiki/AutoCAD). Or you already know something about design, or you prefer to draw things before building them. In either cases, FreeCAD features a more traditional workbench, with tools found in most 2D CAD applications: The [Draft Workbench](http://www.freecadweb.org/wiki/index.php?title=Draft_Module).

The Draft Workbench, although it adopts ways of working inherited from the traditional 2D CAD world, is not limited at all to the 2D realm. All its tools work in the whole 3D space and many of the Draft tools, for example ![icon](http://www.freecadweb.org/wiki/images/thumb/c/c5/Draft_Move.png/16px-Draft_Move.png) [Move](http://www.freecadweb.org/wiki/index.php?title=Draft_Move) or ![icon](http://www.freecadweb.org/wiki/images/thumb/5/5a/Draft_Rotate.png/16px-Draft_Rotate.png) [Rotate](http://www.freecadweb.org/wiki/index.php?title=File:Draft_Rotate.png), are commonly used all over FreeCAD because they are often more intuitive than changing placement parameters manually.

Among the tools offered by the Draft Workbench, you will find traditional drawing tools like ![icon](http://www.freecadweb.org/wiki/images/thumb/a/a8/Draft_Line.png/16px-Draft_Line.png) [Line](http://www.freecadweb.org/wiki/index.php?title=Draft_Line), ![icon](http://www.freecadweb.org/wiki/images/thumb/1/10/Draft_Circle.png/16px-Draft_Circle.png) [Circle](http://www.freecadweb.org/wiki/index.php?title=Draft_Circle), or ![icon](http://www.freecadweb.org/wiki/images/thumb/0/00/Draft_Wire.png/16px-Draft_Wire.png) [Wire](http://www.freecadweb.org/wiki/index.php?title=Draft_Wire) (polyline), modification tools like ![icon](http://www.freecadweb.org/wiki/images/thumb/c/c5/Draft_Move.png/16px-Draft_Move.png) [Move](http://www.freecadweb.org/wiki/index.php?title=Draft_Move), ![icon](http://www.freecadweb.org/wiki/images/thumb/5/5a/Draft_Rotate.png/16px-Draft_Rotate.png) [Rotate](http://www.freecadweb.org/wiki/index.php?title=File:Draft_Rotate.png) or ![icon](http://www.freecadweb.org/wiki/images/thumb/e/eb/Draft_Offset.png/16px-Draft_Offset.png) [Offset](http://www.freecadweb.org/wiki/index.php?title=Draft_Offset), a [working plane/grid system](http://www.freecadweb.org/wiki/index.php?title=Draft_SelectPlane) that allows you to define precisely in which plane you are working, and a complete [snapping system](http://www.freecadweb.org/wiki/index.php?title=Draft_Snap) that makes it very easy to draw and position elements precisely in relation to each other.

To showcase the working and possibilities of the Draft Workbench, we will walk through a simple exercise, the result of which will be this little drawing, showing the floor plan of a small house that contains only a kitchen top (A pretty absurd floor plan, but we can do what we want here, can't we?):

![the final floor plan](http://www.freecadweb.org/wiki/images/3/35/Exercise_cabin_01.jpg)

**Preparations**

Like with all technical drawing applications, it is wise to set up your environment correctly. The Draft Workbench comes with several pages of preferences settings that allow you to save yourself a lot of time by setting everything to the way you like before starting:

* Switch to the **Draft Workbench**
* Choose menu **Edit -> Preferences**. An important thing to know: FreeCAD adopts a **late loading** philosophy: Since workbenches can sometimes be very heavy because they will load a lot of software libraries, they will only load fully the first time you activate them. So the Draft preferences pages will only appear after the Draft Workbench has been loaded. There, you can set a couple of defaults to your liking, such as text and dimensions style.

![Draft options](http://www.freecadweb.org/wiki/images/1/1a/Freecad_draft_options_01.jpg)

* You can also configure the Draft grid which indicates the current [working plane](http://www.freecadweb.org/wiki/index.php?title=Draft_SelectPlane). Each intersection of the grid lines provides a snapping point. As we can see on the image above, our house plan will measure 2 meters by 2 meters. We could leave the grid to its default values of 1 meter between lines. But we could also set it to a more convenient value of 5cm (50mm), which will make almost all our points snappable to the grid.
* The Draft Workbench also has two special toolbars, one to manage **visual settings** and another to change **snap locations**. From there, you can change the current working plane, turn [construction mode](http://www.freecadweb.org/wiki/index.php?title=Draft_ToggleConstructionMode) on/off, set the line color, face color and line weight for new objects, and set individual [Snap locations](http://www.freecadweb.org/wiki/index.php?title=Draft_Snap):

![Draft toolbars](http://www.freecadweb.org/wiki/images/3/39/Draft_toolbars.jpg)

* Let's start by turning construction mode on, which willallow us to draw some guidelines on which we will draw our final geometry.
* Then, select the ![icon](http://www.freecadweb.org/wiki/images/thumb/1/14/Draft_Rectangle.png/16px-Draft_Rectangle.png) [Rectangle](http://www.freecadweb.org/wiki/index.php?title=Draft_Rectangle) tool and draw two rectangles, one of 2 meters by 2 meters, and another 15cm inside. You can do the second one either by drawing another rectangle, or by using the ![icon](http://www.freecadweb.org/wiki/images/thumb/e/eb/Draft_Offset.png/16px-Draft_Offset.png) [Offset](http://www.freecadweb.org/wiki/index.php?title=Draft_Offset) tool, turning its Copy mode on, and giving it a distance of 15cm:

![the first rectangles](http://www.freecadweb.org/wiki/images/f/f0/Exercise_cabin_02.jpg)

**Read more**

* The Draft Workbench: http://www.freecadweb.org/wiki/index.php?title=Draft_Module
* Snapping: http://www.freecadweb.org/wiki/index.php?title=Draft_Snap
