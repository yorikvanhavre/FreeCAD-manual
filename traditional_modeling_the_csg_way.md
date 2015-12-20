## Traditional modeling - the CSG way

CGS stands for [Constructive Solid Geometry](https://en.wikipedia.org/wiki/Constructive_solid_geometry) and describes the most basic way to work with solid 3D geometry, which is creating complex objects by adding and removing pieces to/from solids by using Boolean operations such as union, subtraction or intersection.

As we saw earlier in this manual, FreeCAD can handle many types of geometry, but the preferred and most useful type for the kind of 3D objects that we want to design with FreeCAD, that is, real-world objects, is, without a doubt, solid, [BREP](https://en.wikipedia.org/wiki/Boundary_representation) geometry, that is mainly handled by the [Part Workbench](http://www.freecadweb.org/wiki/index.php?title=Part_Module). Unlike [polygon meshes](https://en.wikipedia.org/wiki/Polygon_mesh), which are made only of points and triangles, BREP objects have their faces defined by mathematical curves, which permits abolute precision, no matter the scale.

![Difference between mesh and brep geometry](http://www.freecadweb.org/wiki/images/1/1a/Mesh_vs_brep.jpg)

The difference between the two can be compared to the difference between bitmap and vectorial images. As with bitmap images, polygon meshes have their curved surfaces fractionned in a series of points. If you look at it from very close, or print it very large, you will see not a curved but a faceted surface. In both vectorial images and BREP data, the position of any point on a curve is not stored in the geometry but calculated on the fly, with exact precision.

In FreeCAD, all BREP-based geometry is handled by another piece of open-source software, [OpenCasCade](https://en.wikipedia.org/wiki/Open_Cascade_Technology). The main interface between FreeCAD and the OpenCasCade kernel is the Part Workbench. Most other workbenches build their functionality on top of Part objects.

Although other workbenches often offer more advanced tools to build and manipulate geometry, since they all actually manipulate Part objects, it is very useful to know how these objects work internally, and be able to use the Part tools since, being more simple, they can very often help you to work around problems that the more intelligent tools fail to solve properly.

To illustrate the working of the Part Workbench, we will model this table, using only CSG operations.
