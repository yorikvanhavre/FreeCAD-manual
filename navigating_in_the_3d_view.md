## Navigating in the 3D view

### A word about the 3D space

If this is your first contact with a 3D application, you will need to grab some concepts first. If not, you can safely skip this section.

The FreeCAD 3D space is an [euclidian space](https://en.wikipedia.org/wiki/Euclidean_space). It has an origin point and three axes: X, Y and Z. If you look at your scene from above, conventionally, the X axis points to the right, the Y axis to the back, and the Z axis upwards. In the lower right corner of the FreeCAD view, you can always see from where you are viewing the scene:

![axes](http://www.freecadweb.org/wiki/images/a/af/Axes_orientation.png) 

Every point of every object that exists in that space can be located by its (x,y,z) coordinates. For example, a point with coordinates (2,3,1) will lie at 2 units on the X axis, 3 units on the Y axis, and 1 unit on the Z axis.

![3d space](http://www.freecadweb.org/wiki/images/4/4a/3dspace_coordinates.jpg)

You can look at that scene from any angle, like if you were holding a camera. That camera can be moved left, right, up and down (pan), rotated around what it is looking at (rotate) and brought closer or further from the scene (zoom).

### The FreeCAD 3D view

Navigating in the FreeCAD 3D view can be done with a mouse, a Space Navigator device, the keyboard, a touchpad, or a combination of those. FreeCAD proposes several 
[navigation modes](http://www.freecadweb.org/wiki/index.php?title=Mouse_Model), which determine how the three basic view manipulation operations (pan, rotate and zoom) are done, as well as how to select objects on the screen are performed. Navigation modes are accessed from the Preferences screen, or directly by right-clicking anywhere on the 3D view:

![Accessing navigation modes](http://www.freecadweb.org/wiki/images/2/2e/Freecad-interface-05.jpg)

Each of these modes attributes different mouse buttons, or mouse + keyboard combinations, or mouse gestures, to these four operations. The following table shows the principal available modes:

| Mode                          | Pan           | Rotate     | Zoom      | Select     |
| ----------------------------- |:-------------:| :---------:|:---------:|:----------:|
| Inventor | ![](http://www.freecadweb.org/wiki/images/7/7e/Select-mouse.svg) | ![](http://www.freecadweb.org/wiki/images/9/92/Rotate-mouse.svg) | ![](http://www.freecadweb.org/wiki/images/b/bf/Zoom-mouse.svg) | CTRL + ![](http://www.freecadweb.org/wiki/images/7/7e/Select-mouse.svg) | 
| CAD (default) | ![](http://www.freecadweb.org/wiki/images/e/e9/Pan-mouse.svg) | ![](http://www.freecadweb.org/wiki/images/9/92/Rotate-mouse.svg) | ![](http://www.freecadweb.org/wiki/images/b/bf/Zoom-mouse.svg) | ![](http://www.freecadweb.org/wiki/images/7/7e/Select-mouse.svg) | 
| Blender | SHIFT + ![](http://www.freecadweb.org/wiki/images/e/e9/Pan-mouse.svg) | ![](http://www.freecadweb.org/wiki/images/e/e9/Pan-mouse.svg) | ![](http://www.freecadweb.org/wiki/images/b/bf/Zoom-mouse.svg) | ![](http://www.freecadweb.org/wiki/images/7/7e/Select-mouse.svg) | 
| Touchpad | SHIFT + ![](http://www.freecadweb.org/wiki/images/7/78/Touchpad.png) | ALT + ![](http://www.freecadweb.org/wiki/images/7/78/Touchpad.png) | PGUP / PGDOWN | ![](http://www.freecadweb.org/wiki/images/b/bb/Select-touchpad.png) |
| Gesture | ![](http://www.freecadweb.org/wiki/images/0/06/Pan-mouse-Ctrl.svg) + DRAG | ![](http://www.freecadweb.org/wiki/images/7/7e/Select-mouse.svg) + DRAG | ![](http://www.freecadweb.org/wiki/images/b/bf/Zoom-mouse.svg) | ![](http://www.freecadweb.org/wiki/images/7/7e/Select-mouse.svg) |

Alternatively, some keyboard controls are always available, no matter the navigation mode: 

 - **CTRL +** and **CTRL -** to zoom in and zoom out 
 - The **arrow keys** to shift the view left/right and up/down 
 - **SHIFT + left arrow** and **SHIFT + right arrow** to rotate the view by 90 degrees 
 - the numeric keys, **1 to 6**, for the six standard views, top, front, right, bottom, back and left
 - **O** will set the camara in orthographic mode, 
 - while **P** sets it in perspective mode. 

These controls are also available from the View menu and some from the View toolbar.

### Selecting objects

Objects in the 3D view can be selected by clicking them with the corresponding mouse button, depending on the navigation mode. A single click will select the object, and one of its subcomponents (edge, face, vertex). Double-clicking will select the object, and all its subcomponents. You can select more than one subcomponent, or even different subcomponents from different objects, by pressing the CTRL key. Clicking with the selection button on an empty portion of the 3D view will deselect everything.

A panel called "Selection view", available from the View menu, can also be turned on, which shows you what is currently selected:

![selection view](http://www.freecadweb.org/wiki/images/c/c5/Selection_view.jpg)

You can also use the Selection View to select objects by searching for a particular object.

**Read more**

* The FreeCAD navigation modes: http://www.freecadweb.org/wiki/index.php?title=Mouse_Model
