## Navigating in the 3D view

Navigating in the FreeCAD 3D view can be done with a mouse, a Space Navigator device, the keyboard,
a touchpad, or a combination of those. FreeCAD proposes several 
[navigation modes](http://www.freecadweb.org/wiki/index.php?title=Mouse_Model), which determine how
the three basic view manipulation operations (pan, rotate and zoom) are done, as well as how to
select objects on the screen are performed. Navigation modes are accessed from the Preferences screen, 
or directly by right-clicking anywhere on the 3D view:

![Accessing navigation modes](http://www.freecadweb.org/wiki/images/2/2e/Freecad-interface-05.jpg)

Each of these modes attributes different mouse buttons, or mouse + keyboard combinations, or
mouse gestures, to these four operations. The following table shows the principal available modes:

| Mode                          | Pan           | Rotate     | Zoom      | Select     |
| ----------------------------- |:-------------:| :---------:|:---------:|:----------:|
| Inventor | ![](http://www.freecadweb.org/wiki/images/7/7e/Select-mouse.svg) | ![](http://www.freecadweb.org/wiki/images/9/92/Rotate-mouse.svg) | ![](http://www.freecadweb.org/wiki/images/b/bf/Zoom-mouse.svg) | CTRL + ![](http://www.freecadweb.org/wiki/images/7/7e/Select-mouse.svg) | 
| CAD (default) | ![](http://www.freecadweb.org/wiki/images/e/e9/Pan-mouse.svg) | ![](http://www.freecadweb.org/wiki/images/9/92/Rotate-mouse.svg) | ![](http://www.freecadweb.org/wiki/images/b/bf/Zoom-mouse.svg) | ![](http://www.freecadweb.org/wiki/images/7/7e/Select-mouse.svg) | 
| Blender | SHIFT + ![](http://www.freecadweb.org/wiki/images/e/e9/Pan-mouse.svg) | ![](http://www.freecadweb.org/wiki/images/e/e9/Pan-mouse.svg) | ![](http://www.freecadweb.org/wiki/images/b/bf/Zoom-mouse.svg) | ![](http://www.freecadweb.org/wiki/images/7/7e/Select-mouse.svg) | 
| Touchpad | SHIFT + ![](http://www.freecadweb.org/wiki/images/7/78/Touchpad.png) | ALT + ![](http://www.freecadweb.org/wiki/images/7/78/Touchpad.png) | PGUP / PGDOWN | ![](http://www.freecadweb.org/wiki/images/b/bb/Select-touchpad.png) |
| Gesture | ![](http://www.freecadweb.org/wiki/images/0/06/Pan-mouse-Ctrl.svg) + DRAG | ![](http://www.freecadweb.org/wiki/images/7/7e/Select-mouse.svg) + DRAG | ![](http://www.freecadweb.org/wiki/images/b/bf/Zoom-mouse.svg) | ![](http://www.freecadweb.org/wiki/images/7/7e/Select-mouse.svg) |

Alternatively, some keyboard controls are always available, no matter the navigation mode: CTRL + and CTRL - to
zoom in and zoom out, the arrow keys to shift the view left/right and up/down, SHIFT + left arrow and SHIFT + right
arrow to rotate the view by 90 degrees, and the numeric keys 1 to 6 for the six standard views, top, front, right,
bottom, back and left. These controls are also avaialbe from the View menu and the View toolbar.

### Selecting objects

Objects in the 3D view can be selected by clicking them with the corresponding mouse button, depending on
the navigation mode. A single click will select the object, and one of its subcomponents (edge, face, vertex).
Double-clicking will select the object, and all its subcomponents. You can select more than one subcomponent, or
even different subcomponents from different objects, by pressing the CTRL key.

**Read more**

* The FreeCAD navigation modes: http://www.freecadweb.org/wiki/index.php?title=Mouse_Model
