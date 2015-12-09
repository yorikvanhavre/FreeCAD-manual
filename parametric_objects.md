## Parametric objects

FreeCAD is designed for parametric modeling. This means that the geometry that you create, instead of being
freely sculptable, is produced by rules and parameters. For example, a cylinder might be produced from a
radius and a height. With these two parameters, the program has enough information to build the geometry.

Parametric objects, in FreeCAD, are in reality small pieces of program, that run whenever one of the
parameters has changed, in order to recompute the shape of the object.

Objects can have a lot of different kinds of parameters: numbers (integers like 1, 2, 3 or floating-point
values like 3.1416), real-world sizes (1mm, 2.4m, 4.5ft), (x,y,z) coordinates, or even another object.

For example, a Pad object takes a 2D shape and an extrusion distance. Then, 

![parametric_modeling](http://www.freecadweb.org/wiki/images/4/47/Parametric_objects.jpg)

**Read more**

* The properties editor: http://www.freecadweb.org/wiki/index.php?title=Property_editor
