## Traditional 2D drafting

You might be interested by FreeCAD because you already have some technical drawing experience, for example with software like [AutoCAD](https://en.wikipedia.org/wiki/AutoCAD). Or you already know something about design, or you prefer to draw things before building them. In either cases, FreeCAD features a more traditional workbench, with tools found in most 2D CAD applications: The [Draft Workbench](http://www.freecadweb.org/wiki/index.php?title=Draft_Module).

The Draft Workbench, although it adopts ways of working inherited from the traditional 2D CAD world, is not limited at all to the 2D realm. All its tools work in the whole 3D space and many of the Draft tools, for example ![icon](http://www.freecadweb.org/wiki/images/thumb/c/c5/Draft_Move.png/16px-Draft_Move.png) [Move](http://www.freecadweb.org/wiki/index.php?title=Draft_Move) or ![icon](http://www.freecadweb.org/wiki/images/thumb/5/5a/Draft_Rotate.png/16px-Draft_Rotate.png) [Rotate](http://www.freecadweb.org/wiki/index.php?title=File:Draft_Rotate.png), are commonly used all over FreeCAD because they are often more intuitive than changing placement parameters manually.

Among the tools offered by the Draft Workbench, you will find traditional drawing tools like ![icon](http://www.freecadweb.org/wiki/images/thumb/a/a8/Draft_Line.png/16px-Draft_Line.png) [Line](http://www.freecadweb.org/wiki/index.php?title=Draft_Line), ![icon](http://www.freecadweb.org/wiki/images/thumb/1/10/Draft_Circle.png/16px-Draft_Circle.png) [Circle](http://www.freecadweb.org/wiki/index.php?title=Draft_Circle), or ![icon](http://www.freecadweb.org/wiki/images/thumb/0/00/Draft_Wire.png/16px-Draft_Wire.png) [Wire](http://www.freecadweb.org/wiki/index.php?title=Draft_Wire) (polyline), modification tools like ![icon](http://www.freecadweb.org/wiki/images/thumb/c/c5/Draft_Move.png/16px-Draft_Move.png) [Move](http://www.freecadweb.org/wiki/index.php?title=Draft_Move), ![icon](http://www.freecadweb.org/wiki/images/thumb/5/5a/Draft_Rotate.png/16px-Draft_Rotate.png) [Rotate](http://www.freecadweb.org/wiki/index.php?title=File:Draft_Rotate.png) or ![icon](http://www.freecadweb.org/wiki/images/thumb/e/eb/Draft_Offset.png/16px-Draft_Offset.png) [Offset](http://www.freecadweb.org/wiki/index.php?title=Draft_Offset), a [working plane/grid system](http://www.freecadweb.org/wiki/index.php?title=Draft_SelectPlane) that allows you to define precisely in which plane you are working, and a complete [snapping system](http://www.freecadweb.org/wiki/index.php?title=Draft_Snap) that makes it very easy to draw and position elements precisely in relation to each other.

To showcase the working and possibilities of the Draft Workbench, we will walk through a simple exercise, the result of which will be this little drawing, showing the floor plan of a small house that contains only a kitchen top (A pretty absurd floor plan, but we can do what we want here, can't we?):

![the final floor plan](http://www.freecadweb.org/wiki/images/3/35/Exercise_cabin_01.jpg)

* Switch to the **Draft Workbench**
* As in all technical drawing applications, it is wise to set up your environment correctly, it will save you a lot of time. Configure the [grid and working plane](http://www.freecadweb.org/wiki/index.php?title=Draft_SelectPlane), [text](http://www.freecadweb.org/wiki/index.php?title=Draft_Text) and [dimensions](http://www.freecadweb.org/wiki/index.php?title=Draft_Dimension) settings to your likings in menu **Edit -> Preferences -> Draft**. In this exercise, however, we will act as if these preference settings were left to their default values.
![Draft options](http://www.freecadweb.org/wiki/images/1/1a/Freecad_draft_options_01.jpg)

* The Draft Workbench also has two special toolbars: One with **visual settings**, where you can change the current working plane, turn [construction mode](http://www.freecadweb.org/wiki/index.php?title=Draft_ToggleConstructionMode) on/off, set the line color, face color, line weight and text size to be used for new objects, and another one with **snap locations**. There, you can turn the grid on/of and set/unset individual [Snap locations](http://www.freecadweb.org/wiki/index.php?title=Draft_Snap):
![Draft toolbars](http://www.freecadweb.org/wiki/images/3/39/Draft_toolbars.jpg)

* Let's start by turning **construction mode** on, which will allow us to draw some guidelines on which we will draw our final geometry.
* Then, select the ![icon](http://www.freecadweb.org/wiki/images/thumb/1/14/Draft_Rectangle.png/16px-Draft_Rectangle.png) [Rectangle](http://www.freecadweb.org/wiki/index.php?title=Draft_Rectangle) tool and draw a rectangle, starting at point (0,0,0), of 2 meters by 2 meters (leave the Z at zero). Note that most of the Draft commands can be fully performed from the keyboard, without touching the mouse, using their two-letter shortcut. Our first 2x2m rectangle can be done like this: `re 0` **Enter** `0` **Enter** `0` **Enter** `2m` **Enter** `2m` **Enter** `0` **Enter**.
* Duplicate that rectangle by 15cm inside, using the ![icon](http://www.freecadweb.org/wiki/images/thumb/e/eb/Draft_Offset.png/16px-Draft_Offset.png) [Offset](http://www.freecadweb.org/wiki/index.php?title=Draft_Offset) tool, turning its Copy mode on, and giving it a distance of 15cm:
![the first rectangles](http://www.freecadweb.org/wiki/images/f/f0/Exercise_cabin_02.jpg)

* We can then draw a couple of vertical lines to define where our doors and windows will be placed, using the ![icon](http://www.freecadweb.org/wiki/images/thumb/a/a8/Draft_Line.png/16px-Draft_Line.png) [Line](http://www.freecadweb.org/wiki/index.php?title=Draft_Line) tool. The crossing of these lines with our two rectangles will give us useful intersections to snap our walls to. Draw the first line from point (15cm, 1m, 0) to point (15cm, 3m, 0).
* Duplicate that line 5 times, using the ![icon](http://www.freecadweb.org/wiki/images/thumb/c/c5/Draft_Move.png/16px-Draft_Move.png) [Move](http://www.freecadweb.org/wiki/index.php?title=Draft_Move) tool with Copy mode turned on. Turn also the Relative mode on, which will allow us to define movements in relative distances, which is eaier than calculate the exact position of each line. Give each new copy any start point, you can leave it at (0,0,0) for example, and the following relative endpoints:
   * line001: x: 10cm
   * line002: x: 120cm
   * line003: x: -55cm, y: -2m
   * line004: x: 80cm
   * line005: x: 15cm
![the window lines](http://www.freecadweb.org/wiki/images/6/60/Exercise_cabin_03.jpg)

* That is all we need now, so we can switch construction mode off. Check that all the construction geometry has been placed into a "Construction" group, which makes it easy to hide it all at once or even delete it completely later on.
* Now let's draw our two wall pieces using the ![icon](http://www.freecadweb.org/wiki/images/thumb/0/00/Draft_Wire.png/16px-Draft_Wire.png) [Wire](http://www.freecadweb.org/wiki/index.php?title=Draft_Wire) tool. Make sure the ![icon](http://www.freecadweb.org/wiki/images/thumb/8/8c/Snap_Intersection.png/16px-Snap_Intersection.png) [intersection snap](http://www.freecadweb.org/wiki/index.php?title=Draft_Snap) is turned on, as we will need to snap to the intersections of our lines and rectangles. Draw two wires as follow, by clicking all the points of their contours. To close them, either click onthe first point again, or press the **Close** button:
![the two walls](http://www.freecadweb.org/wiki/images/b/b8/Exercise_cabin_04.jpg)

* We can change their default grey color to a nice hatch pattern, by selecting both walls, then setting their **Pattern** property to *Simple*, and their **Pattern size** to your liking, for example *0.005*.
![hatch patterns](http://www.freecadweb.org/wiki/images/5/5c/Exercise_cabin_05.jpg)

**Read more**

* The Draft Workbench: http://www.freecadweb.org/wiki/index.php?title=Draft_Module
* Snapping: http://www.freecadweb.org/wiki/index.php?title=Draft_Snap
