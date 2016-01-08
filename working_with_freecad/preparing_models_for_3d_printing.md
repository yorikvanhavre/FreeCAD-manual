## Preparing models for 3D printing

One of the main uses of FreeCAD is to produce real-world objects. These can be designed in FreeCAD, and then made real by different ways, such as communicated to other people who will then build them, or, more and more fequently, sent directly to a [3D printer](https://en.wikipedia.org/wiki/3D_printing) or a [CNC mill](https://en.wikipedia.org/wiki/Milling_%28machining%29). This chapter will show you how to get your models ready to send to these machines.

If you have been cautious while modeling, most of the difficulty you might encounter when printing your model in 3D has already been avoided. This involves basically:

* Making sure that your 3D objects are **solid**. Real-world objects are solid, the 3D model must be solid too. We saw in earlier chapters that FreeCAD helps you a lot in that regard, and that the [Part Design Workbench](http://www.freecadweb.org/wiki/index.php?title=PartDesign_Workbench) will notify you if you do an operation that prevents your model to stay solid.
* Making sure about the **dimensions** of your objects. One millimeter will be one millimeter in real-life. Every dimension matters. 
* Controlling the **degradation**. No 3D printing or CNC milling system can take FreeCAD files directly. Most of them will only understand a machine language called [G-Code](https://en.wikipedia.org/wiki/G-code). G-code has dozens of different dialects, each machine or vendor usually using its own. The conversiom of your models into G-Code can be easy and automatic, but you can also do it manually, with total control over the output. In any case, some loss of quality of your model will unavoidably occur during the process. When printing in 3D, you must always make sure this loss of quality stays below your minimal requirements.

Below, we will assume that the first two criterias are met, and that by now you are able to produce solid objects with correct dimensions. We will now see how to address the third point.

### The easy way, using automatic conversion tools

This is the technique most commonly used for 3D printing. 
