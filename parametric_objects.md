## Parametric objects

FreeCAD is designed for parametric modeling. This means that the geometry that you create, instead of being freely sculptable, is produced by rules and parameters. For example, a cylinder might be produced from a radius and a height. With these two parameters, the program has enough information to build the cylinder.

Parametric objects, in FreeCAD, are in reality small pieces of a program that run whenever one of the parameters has changed. Objects can have a lot of different kinds of parameters: numbers (integers like 1, 2, 3 or floating-point values like 3.1416), real-world sizes (1mm, 2.4m, 4.5ft), (x,y,z) coordinates, text strings ("hello!") or even another object.

This last type allows to quickly build complex chains of operations, each new object being based on a previous one, and adding new features to it.

In the example below, a Pad object is based on a 2D shape (Sketch) and an extrusion distance. With these, it produces an extrusion (pad) of the given 2D shape, by the given distance. You can then use this pad as a base for further operations, such as drawing a new 2D shape on one of its faces (Sketch001) and then making a subtraction (pocket), until arriving at your final object. 

All the intermediary operations (2D shapes, pad, pocket, etc) are still there, and you can still change any of their parameters anytime. The whole chain will be rebuilt (recomputed) whenever needed.

![parametric modeling example](http://www.freecadweb.org/wiki/images/4/47/Parametric_objects.jpg)

Two important things are necessary to know:

1. Recomputation is not always automatic. Heavy operations, that might modify a big portion of your document, and therefore take some time, are not performed automatically. Instead, the object (and all the objects that depend on it) will be marked for recomputation (a small blue icon appears on them in the tree view). You must then press the recompute button to have all the marked objects recomputed.
2. The dependency tree must always flow in the same direction. Loops are forbidden. You can have object A which depends on object B which depend on object C. But you cannot have object A which depends on object B which depends on object A. That would be a circular dependency. However, you can have many objects that depend on the same object, for example objects B and C both depend on A. Menu **Tools -> Dependency graph** shows you a dependency diagram like on the image above. It can be useful to detect problems.

Not all objects are parametric in FreeCAD. Often, the geometry that you import from other files won't contain any parameter, and will be simple, non-parametric objects. However, these can often be used as a base, or starting point for newly created parametric objects, depending, of course, on what the parametric object requires and the quality of the imported geometry.

Finally, it is worth noting that custom parametric objects are [easy to program in python](http://www.freecadweb.org/wiki/index.php?title=Scripted_objects).

**Read more**

* The properties editor: http://www.freecadweb.org/wiki/index.php?title=Property_editor
* How to program parametric objects: http://www.freecadweb.org/wiki/index.php?title=Scripted_objects
* Enabling the dependency graph feature: http://www.freecadweb.org/wiki/index.php?title=Std_DependencyGraph
