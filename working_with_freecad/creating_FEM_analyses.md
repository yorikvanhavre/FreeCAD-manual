## Creating FEM analyses

FEM stands for [Finite Element Method](https://en.wikipedia.org/wiki/Finite_element_method). It is a vast mathematical subject, but in FreeCAD we can resume it as a way to calculate propagations inside a 3D object, by cutting it into small pieces, and analyzing the impact of each small piece over its neighbours. This has several uses in the engineering and electomagnetism fields, but we will look here more in depth at one use that is already well developed in FreeCAD, which is simulating deformations in objects which are submitted to forces and weights.

Obtaining such simulation is done in FreeCAD with the [FEM Workbench](http://www.freecadweb.org/wiki/index.php?title=Fem_Workbench). It involves different steps: Preparing the geometry, setting its material, performing the meshing (division into smaller parts, like we did in the "[Preparing objects for 3D printing](preparing_models_for_3d_printing.md)" chapter, and finally calculating the simulation.

### Preparing FreeCAD

The simulation itself is done by another piece of software, that is used by FreeCAD to obtain the results. As there are several interesting open-source FEM simulation applications available, the [FEM Workbench](http://www.freecadweb.org/wiki/index.php?title=Fem_Workbench) has been made to be able to use more than one. However, currently only [CalculiX](http://www.calculix.de/) is fully implemented. Another piece of software, called [NetGen](https://sourceforge.net/projects/netgen-mesher/), which is responsible for generating the subdivision mesh, is also required. Detailed instructions to install these two components are provided [in the FreeCAD documentation](http://www.freecadweb.org/wiki/index.php?title=FEM_Install).

### Preparing the geometry

**Read more**

* The FEM Workbench: http://www.freecadweb.org/wiki/index.php?title=Fem_Workbench
* Installing required FEM components: http://www.freecadweb.org/wiki/index.php?title=FEM_Install
* CalculiX: http://www.calculix.de/
* NetGen: https://sourceforge.net/projects/netgen-mesher/
