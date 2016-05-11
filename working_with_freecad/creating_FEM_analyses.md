## Creating FEM analyses

FEM stands for [Finite Element Method](https://en.wikipedia.org/wiki/Finite_element_method). It is a vast mathematical subject, but in FreeCAD we can resume it as a way to calculate propagations inside a 3D object, by cutting it into small pieces, and analyzing the impact of each small piece over its neighbours. This has several uses in the engineering and electomagnetism fields, but we will look here more in depth at one use that is already well developed in FreeCAD, which is simulating deformations in objects which are submitted to forces and weights.

Obtaining such simulation is done in FreeCAD with the [FEM Workbench](http://www.freecadweb.org/wiki/index.php?title=Fem_Workbench). It involves different steps: Preparing the geometry, setting its material, performing the meshing (division into smaller parts, like we did in the "[Preparing objects for 3D printing](preparing_models_for_3d_printing.md)" chapter, and finally calculating the simulation.

![fem deformation](http://www.freecadweb.org/wiki/images/4/42/Exercise_fem_01.jpg)

### Preparing FreeCAD

The simulation itself is done by another piece of software, that is used by FreeCAD to obtain the results. As there are several interesting open-source FEM simulation applications available, the [FEM Workbench](http://www.freecadweb.org/wiki/index.php?title=Fem_Workbench) has been made to be able to use more than one. However, currently only [CalculiX](http://www.calculix.de/) is fully implemented. Another piece of software, called [NetGen](https://sourceforge.net/projects/netgen-mesher/), which is responsible for generating the subdivision mesh, is also required. Detailed instructions to install these two components are provided [in the FreeCAD documentation](http://www.freecadweb.org/wiki/index.php?title=FEM_Install).

### Preparing the geometry

We will start with the house we modelled in the [BIM modeling](bim_modeling.md) chapter. However, some changes have to be made to make the model suitable for FEM calculations. This involves, basically, discarding the objects that we don't want to include in the calculaiton, such as the door and window, and joining all the remaining objects into one.

* Load the [house model](https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/house.FCStd) we modeled earlier
* Delete or hide the page object, the section planes and the dimensions, so we stay only with our model
* Hide the window, the door and the ground slab
* Also hide the metal beams from the roof. Since they are very different objects from the rest of the house, we will simplify our calculation by not including it.
* Now let's join the roof slab with the walls. Edit the **Rectangle** object that we used as a base of the roof slab, and change it's **Placement->Position->X** value from 3.18m to 3.00m
* Our model is now clean:

![the clean model](http://www.freecadweb.org/wiki/images/6/65/Exercise_fem_02.jpg)

* The FEM Workbench can currently calculate deformations on one single object only. Therefore, we need to join our two objects (the wall and the slab). Switch to the [Part Workbench](http://www.freecadweb.org/wiki/index.php?title=Part_Module), select the two objects, and press the ![icon](http://www.freecadweb.org/wiki/images/thumb/c/c6/Part_Fuse.png/16px-Part_Fuse.png) [Fuse](http://www.freecadweb.org/wiki/index.php?title=Part_Fuse). We now have obtained one fused object:

![the fused objects](http://www.freecadweb.org/wiki/images/c/c6/Exercise_fem_03.jpg)

**Read more**

* The FEM Workbench: http://www.freecadweb.org/wiki/index.php?title=Fem_Workbench
* Installing required FEM components: http://www.freecadweb.org/wiki/index.php?title=FEM_Install
* CalculiX: http://www.calculix.de/
* NetGen: https://sourceforge.net/projects/netgen-mesher/
