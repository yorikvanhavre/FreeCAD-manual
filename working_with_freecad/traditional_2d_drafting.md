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
* If you wish, set the **working plane** to **XY*. If you do this, the working plane won't change, no matter the current view. If not, the working plane will adapt automatically to the current view, and you should take care of staying in top view whenever you want to draw on the XY (ground) plane.
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

* We can now hide the construction geometry by right-clicking the Construction group and choose **Hide Selection**.
* Let's now draw the windows and doors. Make sure the ![icon](http://www.freecadweb.org/wiki/images/thumb/d/db/Snap_Midpoint.png/16px-Snap_Midpoint.png) [midpoint snap](http://www.freecadweb.org/wiki/index.php?title=Draft_Snap) is turned on, and draw six lines as follow:

![Window lines](http://www.freecadweb.org/wiki/images/d/de/Exercise_cabin_06.jpg)

* We will now change the door line to create an opened door symbol. Start by rotating the line using the ![icon](http://www.freecadweb.org/wiki/images/thumb/5/5a/Draft_Rotate.png/16px-Draft_Rotate.png) [Rotate](http://www.freecadweb.org/wiki/index.php?title=File:Draft_Rotate.png) tool. Click the enpoint of the line as rotation center, give it a start angle of **0**, and an end angle of **-90**.
* Then create the opening arc with the ![icon](http://www.freecadweb.org/wiki/images/thumb/a/a8/Draft_Arc.png/16px-Draft_Arc.png) [Arc](http://www.freecadweb.org/wiki/index.php?title=Draft_Arc) tool. Pick the same point as the rotation center we used in the previous step as center, click the other point of the line to give the radius, then the start and end points as follow:

![the door arc](http://www.freecadweb.org/wiki/images/b/bc/Exercise_cabin_07.jpg)

* We can now start placing some furniture. To begin with, let's place a counter by drawing a rectangle from the upper left inner corner, and giving it a width of 170cm and a height of -60cm. In the image below, the **Transparency** property of the rectangle is set to 80%, to give it a nice furniture look.
* Then let's add a sink and a cooktop. Drawing these kinds of symbols by hand can be very tedious, and they are usually easy to find on the internet, for example on http://www.cad-blocks.net. In the **Downloads** section below, for convenience, we separated a sink and a cooktop from this site, and saved them as DXF files.You can download these two files by visiting the links below, and right-clicking the **Raw** button, then choosing **save as**.
* Inserting a DXF file into an opened FreeCAD document can be done either by choosing the **File -> Import** menu option, or by dragging and dropping the DXF file from your file explorer into the FreeCAD window. The contents of the DXF files might not appear right on the center of your current view, depending on where they were in the DXF file. You can use menu **View -> Standard views -> Fit all** to zoom out and find the imported objects. Insert the two DXF files, and move them to a suitable location on the tabletop:

![the furniture in place](http://www.freecadweb.org/wiki/images/8/86/Exercise_cabin_08.jpg)

* We can now place a couple of dimensions using the ![icon](http://www.freecadweb.org/wiki/images/thumb/b/b0/Draft_Dimension.png/16px-Draft_Dimension.png) [Dimension](http://www.freecadweb.org/wiki/index.php?title=Draft_Dimension) tool. Dimensions are drawn by clicking 3 points: the start point, an end point, and a third point to place the dimension line. To make horizontal or vertical dimensions, even if the two first points are not aligned, press **Shift** while clicking the second point.
* You can change the position of a dimension text by double-clicking the dimension in the tree view. A control point will allow you to move the text graphically. In our exercise, the "0.15" texts have been moved away for better clarity.
* You can change the contents of the dimension text by editing their **Override** property. In our example, the texts of the door and windows dimensions have been edited to indicate their heights:

![the dimensions](http://www.freecadweb.org/wiki/images/f/fb/Exercise_cabin_09.jpg)

* Let's add some description texts using the ![icon](http://www.freecadweb.org/wiki/images/thumb/9/9f/Draft_Text.png/16px-Draft_Text.png) [Text](http://www.freecadweb.org/wiki/index.php?title=Draft_Text) tool. Click a point to position the text, then enter the lines of text, pressing Enter after each line. To finish, press Enter twice.
* The indication lines (also called "leaders") that link the texts to the item they are describing are simply done with the Wire tool. Draw wires, starting from the text position, to the place being described. Once that is done, you can add a bullet or arrow at the end of the wires by setting their **End Arrow** property to **True**

![the indications](http://www.freecadweb.org/wiki/images/2/24/Exercise_cabin_10.jpg)

* Our drawing is now complete! Since there begins to be quite a number of objects there, it would be wise do some cleaning and place everything in a nice structure of groups, to make the file easier to understand to another person:

![order](http://www.freecadweb.org/wiki/images/7/70/Exercise_cabin_11.jpg)

* We can now print our work by placing it on a Drawing sheet, which we will show further in this manual, or directly export our drawing to other CAD applications, by exporting it to a DXF file. Simply select our "Floor plan" group, select menu **File -> Export**, and select the Autodesk DXF format. The file can then be opened in any other 2D CAD application such as [LibreCAD](http://www.librecad.org). You might notice some differences (for example LibreCAD is at the moment unable to express dimension lengths in a specific unit), this can vary from one application to another.

![in librecad](http://www.freecadweb.org/wiki/images/6/65/Exercise_cabin_12.jpg)

* The most important thing about the Draft Workbench, however, is that the geometry you create with it can be used as a base or easily extruded into 3D objects, simply by using the ![icon](http://www.freecadweb.org/wiki/images/thumb/d/df/Part_Extrude.png/16px-Part_Extrude.png) [Extrude](http://www.freecadweb.org/wiki/index.php?title=Part_Extrude) tool from the [Part Workbench](http://www.freecadweb.org/wiki/index.php?title=Part_Module), or, to stay in Draft, the ![icon](http://www.freecadweb.org/wiki/images/thumb/e/e7/Draft_Trimex.png/16px-Draft_Trimex.png) [Trimex](http://www.freecadweb.org/wiki/index.php?title=Draft_Trimex) (Trim/Extend/Extrude) tool, which under the hood performs a Part Extrusion,  but does it "the Draft way", that is, allows you to indicate and snap the extrusion length graphically. 
* By changing the [working plane](http://www.freecadweb.org/wiki/index.php?title=Draft_SelectPlane), for exemple using a face of an extruded object then pressing the Working Plane button, you are also able to place the working plane anywhere, and therefore draw Draft objects in different planes, for example on top of the walls. These can then be extruded to form other3D solids.

![3d on top of draft objects](http://www.freecadweb.org/wiki/images/4/45/Exercise_cabin_13.jpg)

* All kinds of openings can also be done as easily by drawing Draft objects on the faces of walls, then extruding them, then using the boolean tools from the Part Workbench to subtract them from another solid, as we saw in the previous chapter.

Fundamentally, what the Draft Workbench does is provide graphical ways to create basic Part operations. While in Part you will usually position objects by setting their placement property by hand, in Draft you can do it on-screen. There are times when one is better, other times when the other is preferable. Don't forget, you can create [custom toolars](http://www.freecadweb.org/wiki/index.php?title=Interface_Customization) in one of these workbenches, add the tools from the other, and get the best of both worlds.

**Downloads**

* The file created during this exercise: https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/cabin.FCStd
* The sink DXF file: https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/sink.dxf
* The cooktop DXF file: https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/cooktop.dx

**Read more**

* The Draft Workbench: http://www.freecadweb.org/wiki/index.php?title=Draft_Module
* Snapping: http://www.freecadweb.org/wiki/index.php?title=Draft_Snap
* The Draft working plane: http://www.freecadweb.org/wiki/index.php?title=Draft_SelectPlane
