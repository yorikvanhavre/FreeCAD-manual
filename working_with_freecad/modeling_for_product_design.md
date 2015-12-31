## Modeling for product design

[Product design](https://en.wikipedia.org/wiki/Product_design) is originally a comercial term, but in the 3D world, it often means modeling something with the idea to have it [3D-printed](https://en.wikipedia.org/wiki/3D_printing) or, more generally, manufactured by a machine, being a 3D printer or a [CNC machine](https://en.wikipedia.org/wiki/Numerical_control).

When you print objects in 3D, a couple of rules become very important. The first and most obvious one is that your objects must be **solid**. As they will become real, solid objects, this is obvious. Nothing prevent them from being hollow inside, however. But you always have a clear notion of which point is inside the material, and which point is outside.

Another obvious rule is that you must take care of the real **dimensions** of the object. The printed object will have an exact size. You need to make certain of that size. In certain cases, for example when a part of an object will need to fit into another one, a couple of tenths of millimeters too much, and your object won't fit anymore.

A third rule is that, at least at the time we are writing these words, no machine is able to print a whole assembly of objects at once, for example a car engine. The engine will be printed piece by piece, and then the pieces will be assembled together. So when we model for product design, we generally model one piece at a time. In FreeCAD, as generally in the industry, these independent pieces are called parts, and the workbenchwe are going to use for this is the [Part Design Workbench](http://www.freecadweb.org/wiki/index.php?title=PartDesign_Workbench).
