## Creating FEM analyses

FEM stands for [Finite Element Method](https://en.wikipedia.org/wiki/Finite_element_method). It is a vast mathematical subject, but in FreeCAD we can resume it as a way to calculate propagations inside a 3D object, by cutting it into small pieces, and analyzing the impact of each small piece over its neighbours. This has several uses in the engineering and electomagnetism fields, but we will look here more in depth at one use that is already well developed in FreeCAD, which is simulating deformations in objects which are submitted to forces and weights.

Obtaining such simulation is done in FreeCAD with the [FEM Workbench](http://www.freecadweb.org/wiki/index.php?title=Fem_Workbench). It involves different steps: Preparing the geometry, setting its material, performing the meshing (division into smaller parts, like we did in the [Preparing objects for 3D printing](preparing_models_for_3d_printing.md) chapter, and finally calculating the simulation.

![fem deformation](http://www.freecadweb.org/wiki/images/4/42/Exercise_fem_01.jpg)

### Preparing FreeCAD

The simulation itself is done by another piece of software, that is used by FreeCAD to obtain the results. As there are several interesting open-source FEM simulation applications available, the [FEM Workbench](http://www.freecadweb.org/wiki/index.php?title=Fem_Workbench) has been made to be able to use more than one. However, currently only [CalculiX](http://www.calculix.de/) is fully implemented. Another piece of software, called [NetGen](https://sourceforge.net/projects/netgen-mesher/), which is responsible for generating the subdivision mesh, is also required. Detailed instructions to install these two components are provided [in the FreeCAD documentation](http://www.freecadweb.org/wiki/index.php?title=FEM_Install).

### Preparing the geometry

We will start with the house we modelled in the [BIM modeling](bim_modeling.md) chapter. However, some changes have to be made to make the model suitable for FEM calculations. This involves, basically, discarding the objects that we don't want to include in the calculaiton, such as the door and window, and joining all the remaining objects into one.

* Load the [house model](https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/house.FCStd) we modeled earlier
* Delete or hide the page object, the section planes and the dimensions, so we stay only with our model
* Hide the window, the door and the ground slab
* Also hide the metal beams from the roof. Since they are very different objects from the rest of the house, we will simplify our calculation by not including it. Instead, we will consider that the roof slab is directly placed on top of the wall.
* Now move the roof slab down so it rests on top of the wall: Edit the **Rectangle** object that we used as a base of the roof slab, and change it's **Placement→Position→X** value from 3.18m to 3.00m
* Our model is now clean:

![the clean model](http://www.freecadweb.org/wiki/images/6/65/Exercise_fem_02.jpg)

* The FEM Workbench can currently calculate deformations on one single object only. Therefore, we need to join our two objects (the wall and the slab). Switch to the [Part Workbench](http://www.freecadweb.org/wiki/index.php?title=Part_Module), select the two objects, and press the ![icon](http://www.freecadweb.org/wiki/images/thumb/c/c6/Part_Fuse.png/16px-Part_Fuse.png) [Fuse](http://www.freecadweb.org/wiki/index.php?title=Part_Fuse). We now have obtained one fused object:

![the fused objects](http://www.freecadweb.org/wiki/images/c/c6/Exercise_fem_03.jpg)

### Creating the analysis

* We are now ready to start a FEM analysis. Let's switch to the [FEM Workbench](http://www.freecadweb.org/wiki/index.php?title=Fem_Workbench)
* Select the fusion object
* Press the ![icon](http://www.freecadweb.org/wiki/images/thumb/5/57/FEM_Analysis.png/16px-FEM_Analysis.png) [New Analysis](http://www.freecadweb.org/wiki/index.php?title=FEM_Analysis) button
* A new analysis will be created and a settings panels opened. Here you can define the meshing parameters to be used to produce the FEM mesh. The main setting to edit is the **Max Size** which defines the maximum size (in millimeters) of each piece of the mesh. For now, we can leave the default value of 1000:

![meshing parameters](http://www.freecadweb.org/wiki/images/5/58/Exercise_fem_04.jpg)

* After pressing OK and a few seconds of calculaiton, our FEM mesh is now ready:

![FEM mesh](http://www.freecadweb.org/wiki/images/e/e2/Exercise_fem_05.jpg)

* We can now define the material to be applied to our mesh. This is important because depending on the material strength, our object will react differently to forces applied to it. Select the analysis object, and press the ![icon](http://www.freecadweb.org/wiki/images/thumb/1/1e/FEM_Material.png/16px-FEM_Material.png) [New Material](http://www.freecadweb.org/wiki/index.php?title=FEM_Material) button.
* A task panel will open to allow us to choose a material. In the Material drop-down list, choose the **Concrete-generic** material, and press OK.

![the FEM material](http://www.freecadweb.org/wiki/images/5/52/Exercise_fem_06.jpg)

* We are now ready to apply forces. Let's start by specifying which faces are fixed into the ground and can therefore not move. Press the ![icon](http://www.freecadweb.org/wiki/images/thumb/d/d3/FEM_FixedConstraint.png/16px-FEM_FixedConstraint.png) [Fixed Constraint](http://www.freecadweb.org/wiki/index.php?title=FEM_FixedConstraint) button.
* Click on the bottom face of our building and press OK. The bottom face is now indicated as unmovable:

![fixed constraint](http://www.freecadweb.org/wiki/images/a/a0/Exercise_fem_07.jpg)

* We will now add a load on the top face, that could represente, for example, a massive weight being spread on the roof. For this we will use a pressure constraint. Press the ![icon](http://www.freecadweb.org/wiki/images/thumb/4/42/FEM_PressureConstraint.png/16px-FEM_PressureConstraint.png) [Pressure Constraint](http://www.freecadweb.org/wiki/index.php?title=FEM_PressureConstraint) button.
* Click the top face of the roof, set the pressure to **10MPa** (the pressure is applied by square millimeter) and click the OK button. Our force is now applied:

![pressure](http://www.freecadweb.org/wiki/images/a/a2/Exercise_fem_08.jpg)

* We are now ready to start the calculation. Select the **CalculiX** object in the tree view, and press the ![icon](http://www.freecadweb.org/wiki/images/thumb/4/4a/FEM_Calculation.png/16px-FEM_Calculation.png) [Start Calculation](http://www.freecadweb.org/wiki/index.php?title=FEM_Calculation) button.
* In the task panel that will open, click first the **Write .inp file** button to create the input file for CalculiX, then the **Run CalculiX** button. A few moments later, the calculation will be done:

![calculix](http://www.freecadweb.org/wiki/images/c/c2/Exercise_fem_09.jpg)

* We can now look at the results. Close the task panel, and see that a new **Results** object has been added to our analysis.
* Double-click the Results object
* Set the type of result that you want to see on the mesh, for example "absolute displacement", tick the **show** checkbox under **Displacement**, and move the slider next to it. You will be able to see the deformation growing as you apply more force:

![the results](http://www.freecadweb.org/wiki/images/5/53/Exercise_fem_10.jpg)

The results displayed by the FEM workbench are of course currently not enough to perform real-life decisions about structures dimensionning and materials. However, they can already give precious information about how the forces flow through a structure, and which are the weak areas that will bear the more stress.

**Downloads**

* The file created during this exercise: https://github.com/yorikvanhavre/FreeCAD-manual/blob/master/files/fem.FCStd

**Read more**

* The FEM Workbench: http://www.freecadweb.org/wiki/index.php?title=Fem_Workbench
* Installing required FEM components: http://www.freecadweb.org/wiki/index.php?title=FEM_Install
* CalculiX: http://www.calculix.de/
* NetGen: https://sourceforge.net/projects/netgen-mesher/
