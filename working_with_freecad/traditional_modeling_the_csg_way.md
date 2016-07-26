## Traditional modeling - the CSG way

CGS stands for [Constructive Solid Geometry](https://en.wikipedia.org/wiki/Constructive_solid_geometry) and describes the most basic way to work with solid 3D geometry, which is creating complex objects by adding and removing pieces to/from solids by using Boolean operations such as union, subtraction or intersection.

As we saw earlier in this manual, FreeCAD can handle many types of geometry, but the preferred and most useful type for the kind of 3D objects that we want to design with FreeCAD, that is, real-world objects, is, without a doubt, solid, [BREP](https://en.wikipedia.org/wiki/Boundary_representation) geometry, that is mainly handled by the [Part Workbench](http://www.freecadweb.org/wiki/index.php?title=Part_Module). Unlike [polygon meshes](https://en.wikipedia.org/wiki/Polygon_mesh), which are made only of points and triangles, BREP objects have their faces defined by mathematical curves, which permits abolute precision, no matter the scale.

![Difference between mesh and brep geometry](http://www.freecadweb.org/wiki/images/1/1a/Mesh_vs_brep.jpg)

The difference between the two can be compared to the difference between bitmap and vectorial images. As with bitmap images, polygon meshes have their curved surfaces fractionned in a series of points. If you look at it from very close, or print it very large, you will see not a curved but a faceted surface. In both vectorial images and BREP data, the position of any point on a curve is not stored in the geometry but calculated on the fly, with exact precision.

In FreeCAD, all BREP-based geometry is handled by another piece of open-source software, [OpenCasCade](https://en.wikipedia.org/wiki/Open_Cascade_Technology). The main interface between FreeCAD and the OpenCasCade kernel is the Part Workbench. Most other workbenches build their functionality on top of the Part Workbench.

Although other workbenches often offer more advanced tools to build and manipulate geometry, since they all actually manipulate Part objects, it is very useful to know how these objects work internally, and be able to use the Part tools since, being more simple, they can very often help you to work around problems that the more intelligent tools fail to solve properly.

To illustrate the working of the Part Workbench, we will model this table, using only CSG operations (except the screws, for which we will use one of the addons, and the dimensions, which will see in the next chapter):

![Complete table](http://www.freecadweb.org/wiki/images/9/99/Exercise_table_complete.jpg)

Let's create a new document (**Ctrl+N** or menu File -> New Document), switch to the Part Workbench, and begin with the first foot:

* Press the ![icon](http://www.freecadweb.org/wiki/images/thumb/a/a5/Part_Box.png/16px-Part_Box.png) **Box** button
* Select the box, then set the following properties (in the **Data** tab):
   * Length: 80mm (or 8cm, or 0.8m, FreeCAD works in any unit)
   * Width: 80mm
   * Height: 75cm
* Duplicate the box by pressing **Ctrl+C** then **Ctrl+V** (or menu Edit -> Copy and Paste)
* Select the new object that has been created
* Change its position by editing its Placement property:
   * Position x: 8mm
   * Position y: 8mm

You should obtain two high boxes, one 8mm apart from the other:

![The first objects](http://www.freecadweb.org/wiki/images/d/d4/Exercise_table_01.jpg)

* Now we can subtract one from the other: Select the **first** one, that is, the one that will **stay**, then, with the CTRL key pressed, select the **other** one, that will be **subtracted** (the order is important) and press the ![icon](http://www.freecadweb.org/wiki/images/thumb/4/4a/Part_Cut.png/16px-Part_Cut.png) **Cut** button:

![First foot complete](http://www.freecadweb.org/wiki/images/0/00/Exercise_table_02.jpg)

Observe that the newly created object, called "Cut", still contains the two cubes we used as operands. In fact, the two cubes are still there in the document, they have merely been hidden and grouped under the Cut object in the tree view. You can still select them by expanding the arrow next to the Cut object, and, if you wish, turn them visible again by right-clickig them or change any of their properties.

* Now let's create the three other feet by duplicating our base cube 6 other times. Since it is still copied, you can simply paste (Ctrl+V) 6 times. Change their position as follows:
   * cube002: x: 0, y: 80cm
   * cube003: x: 8mm, y: 79.2cm
   * cube004: x: 120cm, y: 0
   * cube005: x: 119.2cm, y: 8mm
   * cube006: x: 120cm, y: 80cm
   * cube007: x: 119.2cm, y: 79.2cm

* Now let's do the three other cuts, selecting first the "host" cube then the cube to be cut off. We now have four Cut objects:

![the four feet](http://www.freecadweb.org/wiki/images/4/43/Exercise_table_03.jpg) 

You might have been thinking that, instead of duplicating the base cube six times, we could have duplicated the complete foot three times. This is totally true, as always in FreeCAD, there are many ways to achieve a same result. This is a precious thing to remember, because, as we will advance into more complex objects, some operations might not give the correct result and we often need to try other ways.

* We will now make holes for the screws, using the same Cut method. Since we need 8 holes, two in each foot, we could make 8 objects to be subtracted. Instead, let's explore other ways and make 4 tubes, that will be reused by two of the feet. So let's create four tubes by using the ![icon](http://www.freecadweb.org/wiki/images/thumb/d/d4/Part_Cylinder.png/16px-Part_Cylinder.png) **Cylinder** tool. You can again, make only one and duplicate it afterwards. Give all cylinders a radius of 6mm. This time, we will need to rotate them, which is also done via the **Placement** property:
  * cylinder: height: 130cm, angle: 90°, axis: x:0,y:1, position: x:-10mm, y:40mm, z:72cm
  * cylinder001: height: 130cm, angle: 90°, axis: x:0,y:1, position: x:-10mm, y:84cm, z:72cm
  * cylinder002: height: 90cm, angle: 90°, axis: x:-1,y:0, position: x:40mm, y:-10mm, z:70cm
  * cylinder003: height: 90cm, angle: 90°, axis: x:-1,y:0, position: x:124cm, y:-10mm, z:70cm

![the cylinders to subtract](http://www.freecadweb.org/wiki/images/3/30/Exercise_table_04.jpg)

You will notice that the cylinders are a bit longer than needed. This is because, as in all solid-based 3D applications, boolean operations in FreeCAD are sometimes oversensitive to face-on-face situations and might fail. By doing this, we put ourselves on the safe side.

* Now let's do the subtractions. Select the first foot, then, with CTRL pressed, select one of the tubes that crosses it, press the **Cut** button. The hole will be done, and the tube hidden. Find it in the tree view by expanding the pierced foot.
* Select another foot pierced by this hidden tube, then repeat the operation, this time Ctrl+ selecting the tube in the tree view, as it is hidden in the 3D view (you can also make it visible again and select it in the 3D view). Repeat this for the other feet until each of them has its two holes:

![the pierced feet](http://www.freecadweb.org/wiki/images/5/57/Exercise_table_05.jpg)

As you can see, each foot has become a quite long series of operations. All this stays parametric, and you can go change any parameter of any of the older operations anytime. In FreeCAD, we often refer to this pile as "modeling history", since it in fact carries all the history of the operations you did. 

Another particularity of FreeCAD is that the concept of 3D object and the concept of 3D operation tend to blend into one same thing. The Cut is at the same time an operation, and the 3D object resulting from this operation. In FreeCAD this is called a "feature", rather than object or operation.

* Now let's do the tabletop, it will be a simple block of wood, let's do it with another **Box** with length: 126cm, width: 86cm, height: 8cm, position: x: 10mm, y: 10mm, z, 67cm. In the **View** tab, you can give it a nice brownish, wood-like color by changing its **Shape Color** property:

![the tabletop](http://www.freecadweb.org/wiki/images/f/f2/Exercise_table_06.jpg)

Notice that, although the legs are 8mm thick, we placed it 10mm away, leaving 2mm between them. This is not necessary, of course, it won't happen with the real table, but it is a common thing to do in that kind of "assembled" models, it helps people who look at the model to understand that these are independent parts, that will need to be attached together manually later.

Now that our five pieces are complete, it is a good time to give them more proper names than "Cut015". By right-clicking the objects in the tree view (or pressing **F2**), you can rename them to something more meaningful to yourself or to another person who would open your file later. It is often said that simlpy giving proper names to your objects is much more important than the way you model them.

* We will now place some screws. There is nowadays an extremely useful addon developed by a member of the FreeCAD community, that you can find on the [FreeCAD addons](https://github.com/FreeCAD/FreeCAD-addons) repository, called [Fasteners](https://github.com/shaise/FreeCAD_FastenersWB), that makes the insertion of screws very easy. Installing additional workbenches is easy and described on the addons pages.
* Once you have installed the Fasteners Workbench and restarted FreeCAD, it will appear in the workbenches list, and we can switch to it. Adding a screw to one of our holes is done by first selecting the circular edge of our hole:

![a selected hole](http://www.freecadweb.org/wiki/images/9/99/Exercise_table_07.jpg)

* Then we can press one of the screw buttons of the Fasteners Workbench, for example the *EN 1665 Hexagon bolt with flanges, heavy series*. The screw will be placed and aligned with our hole, and the diameter will automatically be selected to match the size of our hole. Sometimes the screw will be placed inverted, which we can correct by flipping its **invert** proprty. We can also set its offset to 2mm, to follow the same rule we used between the tabletop and the feet:

![the placed screw](http://www.freecadweb.org/wiki/images/5/54/Exercise_table_08.jpg)

* Repeat this for all the holes, and our table is complete!

**The internal structure of Part objects**

As we saw above, it is possible in FreeCAD to select not only whole objects, but parts for them, such as the circular border of our screw hole. This is a good time to have a quick look at how Part objects are constructed internally. Every workbench that produces Part geometry will be based on these:

* **Vertices**: These are points (usually endpoints) on which all the rest is built. For example, a line has two vertices.
* **Edges**: the edges are linear geometry like lines, arcs, ellipses or [NURBS](https://en.wikipedia.org/wiki/Non-uniform_rational_B-spline) curves. They usually have two vertices, but some special cases have only one (a closed circle for example).
* **Wires**: A wire is a sequence of edges connected by their endpoints. It can contain edges of any type, and it can be closed or not.
* **Faces**: Faces can be planar or curved, and can be formed by one closed wire, which forms the border of the face, or more than one, in case the face has holes.
* **Shells**: Shells are simply a group of faces connected by their edges. It can be open or closed.
* **Solids**: When a shell is tighly closed, that is, it has no "leak", it becomes a solid. Solids carry the notion of inside and outside. Many workbench rely on this to make sure the objects they produce can be built in the real world.
* **Compounds**: Compounds are simply aggegates of other shapes, no matter their type, into a single shape.

In the 3D view, you can select individual **vertices**, **edges** or **faces**. Selecting one of these also selects the whole object.

**A note about shared design**

You might look at the table above, and think its design is not good. The tightening of the feet with the tabletop is probably too weak. You might want to add reforcing pieces, or simply you have other ideas to make it better. This is where sharing becomes interesting. You can download the file made during this exercise from the link below, and modify it to make it better. Then, if you share that improved file, others might be able to make it even better, or use your well-designed table in their projects. Your design might then give other ideas to other people, and maybe you will have helped a tiny bit to make a better world...

**Downloads**

* The file produced in this exercise: https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/table.FCStd

**Read more**

* The Part Workbench: http://www.freecadweb.org/wiki/index.php?title=Part_Module
* The FreeCAD addons repository: https://github.com/FreeCAD/FreeCAD-addons
* The Fasteners Workbench: https://github.com/shaise/FreeCAD_FastenersWB
