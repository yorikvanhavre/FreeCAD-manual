## Creating renderings

In computer talk, a [rendering](https://en.wikipedia.org/wiki/Rendering_%28computer_graphics%29) is a word used to describe a nice image produced from a 3D model. Of course, we could say that what se see in the FreeCAD 3D view is already nice. But anybody who saw a recent Hollywood movie knows that it is possible to produce images with a computer that are almost undistinguishable from a photograph.

Of course, producing such photo-realistic images requires a lot of work, and a 3D application that offers specific tools for that, such as precise controls for materials and lighting. FreeCAD being an application more geared towards technical modeling, it doesn't feature any advanced rendering tool.

Fortunately, the opens-source world offers many applications to produce realistic images. Probably the most famous one is [Blender](http://www.blender.org), which is very popular and widely used in the movies and gaming industries. 3D models can very easily and faithfully be exported from FreeCAD and imported into Blender, where you can add realistic materials and illumination, and produce the final images or even animations.

Some other open-source rendering tools are made to be used inside another application, and will take care of doing the complex calculations to  produce realistic images. Through its [Raytracing Workbench](http://www.freecadweb.org/wiki/index.php?title=Raytracing_Module), FreeCAD can use two of these rendering tools: [POV-Ray](https://en.wikipedia.org/wiki/POV-Ray) and [Luxrender](http://www.luxrender.net). POV-Ray is a very old project, and is considered a classical [raytracing](https://en.wikipedia.org/wiki/Ray_tracing_%28graphics%29) engine, while Luxrender is much newer, and is categorized as an [unbiased](https://en.wikipedia.org/wiki/Unbiased_rendering) renderer. Both have their strengths and weaknesses, depending on the type of image one wants to render. The best way to know is to look at examples on both engines websites.

### Installation

Before being able to use the Raytracing Workbench in FreeCAD, one of these two rendering applications needs to be installed on your system. This is usually very straightforward, both provide installers for many platforms or are usually included in the software repositories of most Linux distributions.

Once POV-Ray or Luxrender is installed, we need to set the path to their main executable in the FreeCAD preferences. This is usually only required on Windows and Mac. On Linux FreeCAD will pick it from the standard locations. The location of the povray or luxrender executables can be found by simply searching your system for files named povray (or povray.exe on Windows) and luxrender (or luxrender.exe on Windows).




**Read more**

* The Raytracing Workbench: http://www.freecadweb.org/wiki/index.php?title=Raytracing_Module
* Blender: http://www.blender.org
* POV-Ray: https://en.wikipedia.org/wiki/POV-Ray
* Luxrender: http://www.luxrender.net
