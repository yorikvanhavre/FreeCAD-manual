## Modeling for product design

[Product design](https://en.wikipedia.org/wiki/Product_design) is originally a comercial term, but in the 3D world, it often means modeling something with the idea to have it [3D-printed](https://en.wikipedia.org/wiki/3D_printing) or, more generally, manufactured by a machine, being a 3D printer or a [CNC machine](https://en.wikipedia.org/wiki/Numerical_control).

When you print objects in 3D, it is of ultimate importance that your objects are **solid**. As they will become real, solid objects, this is obvious. Nothing prevent them from being hollow inside, of course. But you always need to have a clear notion of which point is inside the material, and which point is outside, because the 3D printer or the CNC machine needs to know exactly what is filled with material and what is not. For this reason, in FreeCAD, the [Part Design Workbench](http://www.freecadweb.org/wiki/index.php?title=PartDesign_Workbench) is the perfect tool to build such pieces, because it will always take care for you that your objects stay solid and buildable.

To illustrate how the PartDesign Workbench works, let's model this well-known piece of [Lego](https://en.wikipedia.org/wiki/Lego):

![the Lego piece](http://www.freecadweb.org/wiki/images/c/c5/Exercise_lego_01.jpg)

The cool thing with Lego pieces is that the dimensions are easy to obtain on the internet, at least for the standard pieces. These are pretty easy to model and print on a 3D printer, and with a bit of patience (3D printing often requires much adjustment and fine-tuning) you can make pieces that are totally compatible and click perfectly into original Lego blocks.In the example below, we will make a piece that is 1.5 times bigger than the original.

We will now use exclusively the [Sketcher](http://www.freecadweb.org/wiki/index.php?title=Sketcher_Module) and [Part Design](http://www.freecadweb.org/wiki/index.php?title=PartDesign_Workbench) tools. Since all the tools from the Sketcher Workbench are also included in the Part Design Workbench, we can stay in Part Design and we will not need to switch back and forth between the two.

Part Design objects are fully based on **Sketches**. A Sketch is a 2D object, made of linear segments (lines, arcs of circle or ellipses) and constraints. These constraints can be applied either on linear segments or on their endpoints or center points, and will force the geometry to adopt certain rules. For example, you can place a vertical constraint on a line segment to force it to stay vertical, or a position (lock) constraint on an endpoint to prohibit it to move. When a sketch has an exact amount of constraints that prohibits any point of the sketch to be moved anymore, we talk about a fully constrained sketch. when there are redundant constraints, that could be removed without allowing the geometry to be moved, it is called over-constrained. This should be avoided, and FreeCAD will notify you if such case occurs.

Sketches have an edit mode, where their geometry and constraints can be changed. When you are done with editing, and leave edit mode, sketches behaves like any other FreeCAD object, and can be used as building blocks for all the Part Design tools, but also in other workbenches, such as [Part](http://www.freecadweb.org/wiki/index.php?title=Part_Module) or [Arch](http://www.freecadweb.org/wiki/index.php?title=Arch_Module). The [Draft Workbench](http://www.freecadweb.org/wiki/index.php?title=Draft_Module) also has a tool that converts Draft objects to Sketches, and vice-versa.

* Let's start by modeling a cubic shape that will be the base of our Lego brick. Later on we will carve the insides, and add the 8 dots on top of it. So let's start this by making a rectangular sketch that we will then extrude:
* Switch to the [Part Design Workbench](http://www.freecadweb.org/wiki/index.php?title=PartDesign_Workbench)
* Click on the ![icon](http://www.freecadweb.org/wiki/images/thumb/4/46/Sketcher_NewSketch.png/16px-Sketcher_NewSketch.png) [New Sketch](http://www.freecadweb.org/wiki/index.php?title=Sketcher_NewSketch) button. A dialog will appear asking where you want to lie the sketch, choose the **XY** plane, which is the "ground" plane. The sketch will be created and will immediately be switched to edit mode, and the view will be rotated to look at your sketch orthogonally.
* Now we can draw a rectangle, by selecting the ![icon](http://www.freecadweb.org/wiki/images/thumb/a/ad/Sketcher_CreateRectangle.png/16px-Sketcher_CreateRectangle.png) [Rectangle](http://www.freecadweb.org/wiki/index.php?title=Sketcher_Rectangle) tool and clicking 2 corner points. You can place the two points anywhere, since their correct location will be set in the next step.
* You will notice that a couple of constraints have automatically been added to our rectangle: the vertical segments have received a vertical constraint, the horizontal ones a horizontal constraint, and each corner a point-on-point constraint that glues the segments together. You can experiment moving the rectangle around by dragging its lines with the mouse, all the geometry will keep obeying the constraints.

![the first sketch](http://www.freecadweb.org/wiki/images/a/aa/Exercise_lego_02.jpg)

* Now, let's add three more constraints:
   * Select one of the vertical segments and add a ![icon](http://www.freecadweb.org/wiki/images/thumb/b/ba/Constraint_VerticalDistance.png/16px-Constraint_VerticalDistance.png) [Vectical Distance Constraint](http://www.freecadweb.org/wiki/index.php?title=Constraint_VerticalDistance). Give it a size of 23.7mm.
   * Select one of the horizontal segments and add a ![icon](http://www.freecadweb.org/wiki/index.php?title=File:Constraint_HorizontalDistance.png) [Horizontal Distance Constraint](http://www.freecadweb.org/wiki/index.php?title=Constraint_HorizontalDistance). Make it 47.7mm.
   * Finally, select one of the corner points, then the origin point (which is the dot at the crossing of the red and green axes), then add a ![icon](http://www.freecadweb.org/wiki/images/thumb/e/e3/Constraint_PointOnPoint.png/16px-Constraint_PointOnPoint.png) [Point-on-Point Constraint](http://www.freecadweb.org/wiki/index.php?title=Constraint_PointOnPoint). The rectangle will then jump to the origin point, and your sketch will turn green, meaning it is now fully constrained. You can try moving its lines or points, nothing will move anymore.

![fully constrained sketch](http://www.freecadweb.org/wiki/images/6/64/Exercise_lego_03.jpg)

Note that the last point-on-point constraint was not absolutely necessary. You are never forced to work with fully constrained sketches. However, if we are going to print this block in 3D, it will be necessary to maintain our piece close to the origin point (which will be the center of the space where the printer head can move). By adding that constraint we are making sure that our piece will always stay "anchored" to that origin point.

* Our base sketch is now ready, we can leave edit mode by pressing the **Close** button on top of its task panel, or simply by pressing the **Escape** key. If needed later on, we can reenter edit mode anytime by double-clicking the sketch in the tree view.
* Let's extrude it by using the ![icon](http://www.freecadweb.org/wiki/images/thumb/7/7e/PartDesign_Pad.png/16px-PartDesign_Pad.png) [Pad](http://www.freecadweb.org/wiki/index.php?title=PartDesign_Pad) tool, and giving it a distance of 14.4mm. The other options can be left at their default values:

![the first pad](http://www.freecadweb.org/wiki/images/8/82/Exercise_lego_04.jpg)

The **Pad** behaves very much like the [Part Extrude](http://www.freecadweb.org/wiki/index.php?title=Part_Extrude) tool that we used in the previous chapter. There are a couple of differences, though, the main one being that a pad cannot be moved. It is attached forever to its sketch. If you want to change the position of the pad, you must move the base sketch. In the current context, where we want to be sure nothing will move out of position, this is an additional security.

**Read more**

* The Sketcher: http://www.freecadweb.org/wiki/index.php?title=Sketcher_Module
* The Part Design Workbench: http://www.freecadweb.org/wiki/index.php?title=PartDesign_Workbench
