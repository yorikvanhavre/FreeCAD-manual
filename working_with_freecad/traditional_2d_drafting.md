## Traditional 2D drafting

You might be interested in FreeCAD because you already have some technical drawing experience, for example with software like [AutoCAD](https://en.wikipedia.org/wiki/AutoCAD), or you already know something about design, or you prefer to draw things before building them. In any case, FreeCAD features a more traditional workbench, with tools found in most 2D CAD applications: The [Draft Workbench](http://www.freecadweb.org/wiki/index.php?title=Draft_Module).

The Draft Workbench, although it adopts ways of working inherited from the traditional 2D CAD world, is not limited to the 2D realm. All its tools work in the whole 3D space and many of the Draft tools, for example ![icon](http://www.freecadweb.org/wiki/images/thumb/c/c5/Draft_Move.png/16px-Draft_Move.png) [Move](http://www.freecadweb.org/wiki/index.php?title=Draft_Move) or ![icon](http://www.freecadweb.org/wiki/images/thumb/5/5a/Draft_Rotate.png/16px-Draft_Rotate.png) [Rotate](http://www.freecadweb.org/wiki/index.php?title=Draft_Rotate), are commonly used elsewhere in FreeCAD because they are often more intuitive than changing placement parameters manually.

Among the tools offered by the Draft Workbench, you will find traditional drawing tools like
 ![icon](http://www.freecadweb.org/wiki/images/thumb/a/a8/Draft_Line.png/16px-Draft_Line.png) [Line](http://www.freecadweb.org/wiki/index.php?title=Draft_Line), 
 ![icon](http://www.freecadweb.org/wiki/images/thumb/1/10/Draft_Circle.png/16px-Draft_Circle.png) [Circle](http://www.freecadweb.org/wiki/index.php?title=Draft_Circle), or 
 ![icon](http://www.freecadweb.org/wiki/images/thumb/0/00/Draft_Wire.png/16px-Draft_Wire.png) [Wire](http://www.freecadweb.org/wiki/index.php?title=Draft_Wire) (polyline.) 
 
 Modification tools like 
 ![icon](http://www.freecadweb.org/wiki/images/thumb/c/c5/Draft_Move.png/16px-Draft_Move.png) [Move](http://www.freecadweb.org/wiki/index.php?title=Draft_Move), 
 ![icon](http://www.freecadweb.org/wiki/images/thumb/5/5a/Draft_Rotate.png/16px-Draft_Rotate.png) [Rotate](http://www.freecadweb.org/wiki/index.php?title=Draft_Rotate) or 
 ![icon](http://www.freecadweb.org/wiki/images/thumb/e/eb/Draft_Offset.png/16px-Draft_Offset.png) [Offset](http://www.freecadweb.org/wiki/index.php?title=Draft_Offset), 
 
 This work bench contains a [working plane/grid system](http://www.freecadweb.org/wiki/index.php?title=Draft_SelectPlane) that allows you to define precisely in which plane you are working, and a complete [snapping system](http://www.freecadweb.org/wiki/index.php?title=Draft_Snap) that makes it very easy to draw and position elements precisely in relation to each other.

To showcase the working and possibilities of the Draft Workbench, we will walk through a simple exercise, the result of which will be this little drawing, showing the floor plan of a small house that contains only a kitchen counter top (A pretty absurd floor plan, but we can do what we want here, can't we?):

![the final floor plan](http://www.freecadweb.org/wiki/images/3/35/Exercise_cabin_01.jpg)

It is presumed that the previous table exercise has been preformed and there will be less explanation of skills already covered.

* Start FreeCAD, create a new drawing,  and switch to the **Draft Workbench**
* As in all technical drawing applications, it is wise to set up your environment correctly, beforehand, it will save a lot of time. Configure the [grid and working plane](http://www.freecadweb.org/wiki/index.php?title=Draft_SelectPlane), [text](http://www.freecadweb.org/wiki/index.php?title=Draft_Text) and [dimensions](http://www.freecadweb.org/wiki/index.php?title=Draft_Dimension) settings to your liking in menu **Edit -> Preferences -> Draft**(large icon in the left hand column). In this exercise, however, the default values are good.

![Draft options](http://www.freecadweb.org/wiki/images/1/1a/Freecad_draft_options_01.jpg)

* The Draft Workbench also has two special toolbars: One with **visual settings**, where you can change the current working plane, turn [construction mode](http://www.freecadweb.org/wiki/index.php?title=Draft_ToggleConstructionMode) on/off, set the line color, face color, line weight and text size to be used for new objects, and another one with **snap locations**. There, you can turn the grid on/off and set/unset individual [Snap locations](http://www.freecadweb.org/wiki/index.php?title=Draft_Snap)   Snaps allow us to precisely set the position of a mouse click based on established geometry.  Snaps are available for the midpoint of a line, the intersection of two lines, the end of a line and others:

![Draft toolbars](http://www.freecadweb.org/wiki/images/3/39/Draft_toolbars.jpg)

* Let's start by turning **construction mode** on, using the ![icon](http://www.freecadweb.org/wiki/images/7/76/Draft_ToggleConstructionMode.png) icon which will allow us to draw some guidelines, locating features of our final geometry.
* Set the **working plane** to **XY*. (Click on the field showing Auto and click on ***XY***) The working plane won't change, no matter the current isometric view. If left in Auto, the working plane would change automatically to the current view.  And you would be forced to insure  you are in top view whenever you wanted to draw on the XY (floor or ground) plane.
* Then, select the ![icon](http://www.freecadweb.org/wiki/images/thumb/1/14/Draft_Rectangle.png/16px-Draft_Rectangle.png) [Rectangle](http://www.freecadweb.org/wiki/index.php?title=Draft_Rectangle) tool and draw a rectangle, starting at point (0,0,0), of 2 meters by 2 meters (leave the Z at zero). (Enter the start point, in the fields to the left, insure the ***Filled ***selection is not checked and click on ***Enter Point ***field.  Enter the diagonal point X=2, Y=2, Z=0 and click on ***Enter Point ***field.  You should see a rectangle and it may be filled in.  Expand out the **Construction **in the model tree and insure the **Rectangle** is highlighted.  In the **Data** tab scroll down to **Make Face** Property and click in the value field.  Change the pull down list to **false**.)

[comment]: <> (Note that most of the Draft commands can be fully performed from the keyboard, without touching the mouse, using their two-letter shortcut. Our first 2x2m rectangle can be done like this: `re 0` **Enter** `0` **Enter** `0` **Enter** `2m` **Enter** `2m` **Enter** `0` **Enter**.)

[comment]: <> (Tracker issue 2810 reported 5Dec15 gwr)

* Duplicate a rectangle 15cm inside the first
Insure Rectangle is highlighted in the model tree,
Using the ![icon](http://www.freecadweb.org/wiki/images/thumb/e/eb/Draft_Offset.png/16px-Draft_Offset.png) [Offset](http://www.freecadweb.org/wiki/index.php?title=Draft_Offset) tool, 
Click on **Copy** mode first in the **Offset Task **tab, 
Move the cursor inside the rectangle to select inside vs outside and
Enter a distance of 15cm on the keyboard
Press **Enter**

* Select Rectangle001 in the model tree and change the **Make Face** property false:

![the first rectangles](http://www.freecadweb.org/wiki/images/f/f0/Exercise_cabin_02.jpg)

* We can then draw a couple of vertical lines to define where our doors and windows will be placed, using the ![icon](http://www.freecadweb.org/wiki/images/thumb/a/a8/Draft_Line.png/16px-Draft_Line.png) [Line](http://www.freecadweb.org/wiki/index.php?title=Draft_Line) tool. The crossing of these lines with our two rectangles will give us useful intersections to snap our walls to. 

* Select the line icon
In the window on the left, labled Line, insure the Relative check box is unchecked.
Enter the start point data (15cm, 1m, 0) 
Select **Enter Point**, note bottom left text changes to **Pick Next Point:**
Enter the end point data (15cm, 3m, 0).
Select **Enter Point** to complete line.

* Duplicate that line 5 times, using the ![icon](http://www.freecadweb.org/wiki/images/thumb/c/c5/Draft_Move.png/16px-Draft_Move.png) [Move](http://www.freecadweb.org/wiki/index.php?title=Draft_Move) tool with Copy mode turned on. 

* As always, insure the original object is highlighted in the Model tree, before selecting the Move icon.
Give each new copy any start point, you can leave it at (0,0,0) for example.  
Turn on **Copy**   
Select **Enter Point**. 
In the new window, Copy should already be on.  Text in bottom left corner should change to **Pick End Point:**
Also turn on Relative mode, which will allow us to define movements in relative distances, which is easier than calculating the exact position of each line.  
Use the following relative endpoints, (Highlight the last line in the model tree before pressing the next Move icon, each moved copy references the previous line) click on **Enter Point** to complete:
   * line001: x: 10cm, (y: 0, z: 0)
   * line002: x: 120cm
   * line003: x: -55cm, y: -2m
   * line004: x: 80cm
   * line005: x: 15cm

![the window lines](http://www.freecadweb.org/wiki/images/6/60/Exercise_cabin_03.jpg)

* That is all we need now, so we can switch off construction mode. Check that all the construction geometry has been placed into a "Construction" group, which makes it easy to hide all at once or even delete completely later.

 * Now would be a good time for an incremental file save, as we discussed in the previous chapter.
 
* Now let's draw our two wall pieces using the ![icon](http://www.freecadweb.org/wiki/images/thumb/0/00/Draft_Wire.png/16px-Draft_Wire.png) [Wire](http://www.freecadweb.org/wiki/index.php?title=Draft_Wire) tool. Make sure the ![icon](http://www.freecadweb.org/wiki/images/thumb/8/8c/Snap_Intersection.png/16px-Snap_Intersection.png) [intersection snap](http://www.freecadweb.org/wiki/index.php?title=Draft_Snap) is turned on, as we will need to snap to the intersections of our lines and rectangles. Draw two wires as follows, by clicking all the points of their contours. To close them, either click on the first point again, or press the **Close** button:

Choose the correct **Close **button.  Not the one above the left side DWire window title.  The **Undo** button will allow you to delete the last point if the point fell off the intersection snap.  You may zoom in close with the mouse wheel to insure the point was placed correctly.  Also watch the Global X,Y,&Z numbers if there are decimal fractions in this simple example you've fallen off the snap. 

![the two walls](http://www.freecadweb.org/wiki/images/b/b8/Exercise_cabin_04.jpg)

* We can change their default grey color to a nice hatch pattern, by selecting both walls, (highlighting both DWires in the model tree) then setting their **Pattern** property (in the View tab) to *Simple*, and their **Pattern size** to your liking, for example *0.005*.  (you may be limited to 2 decimal digits of precision so use 0.01 and the crosshatch will not be visible until you zoom in enough.)

![hatch patterns](http://www.freecadweb.org/wiki/images/5/5c/Exercise_cabin_05.jpg)

* We can now hide the construction geometry by selecting the Construction group and in the View top menu, select **Toggle visibility**.
* Let's now draw the windows and doors. 
* Unselect the Intersection Snap icon ![icon](http://www.freecadweb.org/wiki/images/8/8c/Snap_Intersection.png) 
* Make sure the ![icon](http://www.freecadweb.org/wiki/images/thumb/d/db/Snap_Midpoint.png/16px-Snap_Midpoint.png) [midpoint snap](http://www.freecadweb.org/wiki/index.php?title=Draft_Snap) is turned on, and use the line tool ![icon](http://www.freecadweb.org/wiki/images/thumb/a/a8/Draft_Line.png/16px-Draft_Line.png) to draw two centered lines as follows:

![Window lines](http://www.freecadweb.org/wiki/images/d/de/Exercise_cabin_06.jpg)

* Unselect the Midpoint Snap icon ![icon](http://www.freecadweb.org/wiki/images/thumb/d/db/Snap_Midpoint.png/16px-Snap_Midpoint.png)
* Select the End Point Snap  ![icon](http://www.freecadweb.org/wiki/images/archive/6/67/20150122200510%21Draft_Endpoint.png)  and add the 4 inner and outer lines.
* Select one of the inner/outer lines just added.  Press control and select another inner/outer line.  Continue pressing control and selecting additional inner/outer lines until you have them all.
* On the left side in the View tab select in the Property side of the Line Color, and choose a less black color.
* We will now change the door line to create an opened door symbol.  In the geometry window select the middle line in the door way.   Start by rotating the line using the ![icon](http://www.freecadweb.org/wiki/images/thumb/5/5a/Draft_Rotate.png/16px-Draft_Rotate.png) [Rotate](http://www.freecadweb.org/wiki/index.php?title=Draft_Rotate) tool. Click the enpoint of the line as rotation center, Ensure copy is not selected, give it a start angle of **0**, **Enter **and an end angle of **-90** **Enter**,
* Then create the opening arc with the ![icon](http://www.freecadweb.org/wiki/images/thumb/a/a8/Draft_Arc.png/16px-Draft_Arc.png) [Arc](http://www.freecadweb.org/wiki/index.php?title=Draft_Arc) tool. Pick the same point as the rotation center we used in the previous step as center, set the radius by selecting the  other point of the line, then the start angle 180 degrees **Enter** and the Aperture -90 degrees **Enter ** as follows:

![the door arc](http://www.freecadweb.org/wiki/images/b/bc/Exercise_cabin_07.jpg)

* Insure Arc is still highlighted in the Model tree,  if not, select it in the geometry window, in the View tab change the Draw Style property to Dashed in the pull down list.
* As discussed previously, an incremental save might be in order.
* We can now start placing some furniture. To begin with, let's place a counter by drawing a rectangle from the upper left inner corner, and giving it a width of 170cm and a height of -60cm. The rectangle should still be highlighted in the Model Tree.  In the View tab, set the **Transparency ** property to 80%,  to set it apart from the wall geometry.
* Then let's add a sink and a cooktop. Drawing these kinds of symbols by hand can be very tedious, and they are usually easy to find on the internet, for example on http://www.cad-blocks.net. In the **Downloads** section below, for convenience, we separated a sink and a cooktop from this site, and saved them as DXF files.  Download these two files by visiting the links below, and right-clicking the **View Raw** link, then choosing **save as**.
* Inserting a DXF file into an opened FreeCAD document can be done either by choosing the **File -> Import** menu option, or by dragging and dropping the DXF file from your file explorer into the FreeCAD window. The contents of the DXF files might not appear right on the center of your current view, depending on where they were in the DXF file. You can use menu **View -> Standard views -> Fit all** to zoom out and find the imported objects. Insert the two DXF files, and move them to a suitable location on the counter top.  Insure the item is highlighted in the Model tree and use the Move icon to change the position, giving a start and finish.  Verify that the Copy selection in the left window is off if you do not want another copy in the drawing:

![the furniture in place](http://www.freecadweb.org/wiki/images/8/86/Exercise_cabin_08.jpg)

* We can now place a couple of dimensions using the ![icon](http://www.freecadweb.org/wiki/images/thumb/b/b0/Draft_Dimension.png/16px-Draft_Dimension.png) [Dimension](http://www.freecadweb.org/wiki/index.php?title=Draft_Dimension) tool. Dimensions are drawn by clicking 3 points: the start point, an end point, and a third point to place the dimension line. In this drawing the dimension text will likely be too small to read.  Insure the Dimension is highlighted in the Model tree.  Below in the View tab, make the font size reasonable.  For a 2m model, about 5% would be a good starting point, which would be 10 cm Font Size.  Adjust up/down to taste.  After a number of dimension font size changes you may want to make a change to your preferences, top Edit Menu --> Preferences ... --> Draft --> Texts and dimensions tab.  If a horizontal dimension is upside down, click from left to right instead of right to left.  To make horizontal or vertical dimensions, even if the two first points are not aligned, press **Shift** while clicking the second point.
* You can change the position of a dimension text by double-clicking the dimension in the tree view. A control point will allow you to move the text graphically. In our exercise, the "0.15" texts have been moved away for better clarity.
* You can change the contents of the dimension text by editing their **Override** property. In our example, the texts of the door and windows dimensions have been edited to indicate their heights (select the dimension in the Model tree, in the View tab scroll to find the **Override** property):

![the dimensions](http://www.freecadweb.org/wiki/images/f/fb/Exercise_cabin_09.jpg)

* Let's add some description texts using the ![icon](http://www.freecadweb.org/wiki/images/thumb/9/9f/Draft_Text.png/16px-Draft_Text.png) [Text](http://www.freecadweb.org/wiki/index.php?title=Draft_Text) tool. Click a point to position the text, then enter the lines of text, pressing Enter after each line. To finish, press Enter twice.
* The indication lines (also called "leaders") that link the texts to the item they are describing are simply done with the Wire tool. Draw line, or Dwire, ***starting from the text position, to the place being described***. Once that is done, you can add a dot or arrow at the **end** of the wires by setting their **End Arrow** property to **True**

![the indications](http://www.freecadweb.org/wiki/images/2/24/Exercise_cabin_10.jpg)

* Our drawing is now complete! (Good time for an incremental save.)  Since there begins to be quite a number of objects there, it would be wise do some cleaning and place everything in a nice structure of groups, to make the file easier to understand to another person.  Right click on the top entry in the model tree, aka the file name, and select Create Group . . . . At the bottom of the Model tree will be a new group.  Right click on the new group and select **Rename**  Let's use Annotations for the new name.  You can now drag and drop items from the Model tree into the new Annotations group, such as Text and Text 001, you will see a + come up when you are over the new group:

![order](http://www.freecadweb.org/wiki/images/7/70/Exercise_cabin_11.jpg)

* We can now print our work by placing it on a Drawing sheet, which we will show further in this manual, or directly export our drawing to other CAD applications, by exporting it to a DXF file. Simply select our "Floor plan" group, (or highlight the the desired elements in the Model tree) and select menu **File -> Export**, and select the Autodesk DXF format, give it a unique, descriptive file name and select  **Save**. The file can then be opened in any other 2D CAD application such as [LibreCAD](http://www.librecad.org). You might notice some differences, depending on the configurations of each application.

![in librecad](http://www.freecadweb.org/wiki/images/6/65/Exercise_cabin_12.jpg)

* The most important thing about the Draft Workbench, however, is that the geometry you create with it can be used as a base or easily extruded into 3D objects, simply by using the ![icon](http://www.freecadweb.org/wiki/images/thumb/d/df/Part_Extrude.png/16px-Part_Extrude.png) [Extrude](http://www.freecadweb.org/wiki/index.php?title=Part_Extrude) tool from the [Part Workbench](http://www.freecadweb.org/wiki/index.php?title=Part_Module), or, to stay in Draft, the ![icon](http://www.freecadweb.org/wiki/images/thumb/e/e7/Draft_Trimex.png/16px-Draft_Trimex.png) [Trimex](http://www.freecadweb.org/wiki/index.php?title=Draft_Trimex) (Trim/Extend/Extrude) tool, which under the hood performs a Part Extrusion,  but does it "the Draft way", that is, allows you to indicate and snap the extrusion length graphically. Experiment extruding our walls as shown below. 
* By pressing the ![icon](http://www.freecadweb.org/wiki/images/thumb/a/aa/Draft_SelectPlane.png/16px-Draft_SelectPlane.png) [working plane](http://www.freecadweb.org/wiki/index.php?title=Draft_SelectPlane) button after selecting a face of an object, you are also able to place the working plane anywhere, and therefore draw Draft objects in different planes, for example on top of the walls. These can then be extruded to form other3D solids. Experiment setting the working plane on one of the top faces of the walls, then draw some rectangles up there. 

![3d on top of draft objects](http://www.freecadweb.org/wiki/images/4/45/Exercise_cabin_13.jpg)

* All kinds of openings can also be done as easily by drawing Draft objects on the faces of walls, then extruding them, then using the boolean tools from the Part Workbench to subtract them from another solid, as we saw in the previous chapter.

Fundamentally, what the Draft Workbench does is provide graphical ways to create basic Part operations. While in Part you will usually position objects by setting their placement property by hand, in Draft you can do it on-screen. There are times when one is better, other times when the other is preferable. Don't forget, you can create [custom toolbars](http://www.freecadweb.org/wiki/index.php?title=Interface_Customization) in one of these workbenches, add the tools from the other, and get the best of both worlds.

**Downloads**

* The file created during this exercise: https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/cabin.FCStd
* The sink DXF file: https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/sink.dxf
* The cooktop DXF file: https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/cooktop.dxf
* The final DXF file produced during this exercise: https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/cabin.dxf

**Read more**

* The Draft Workbench: http://www.freecadweb.org/wiki/index.php?title=Draft_Module
* Snapping: http://www.freecadweb.org/wiki/index.php?title=Draft_Snap
* The Draft working plane: http://www.freecadweb.org/wiki/index.php?title=Draft_SelectPlane
