# Working with FreeCAD

## All workbenches at a glance

One of the biggest difficulty for new users of FreeCAD, is to know in which workbench to find a specific tool. The table below will give you an overview of the most important workbenches and their tools. Refer to each workbench page in the FreeCAD documentation for a more complete list.

**Draft**

The Draft workbench provides tools to do basic 2D CAD drafting tasks: lines, circles, etc... and a series of generic handy tools such as move, rotate or scale. It also provides several 
drawing aids, such as grid and snapping.

| Tool | Description | Tool | Description |
| ---- | ----------- | ---- | ----------- |
| ![icon](http://www.freecadweb.org/wiki/images/a/a8/Draft_Line.png) [Line](http://www.freecadweb.org/wiki/index.php?title=Draft_Line) | Draws a line segment between 2 points | ![icon](http://www.freecadweb.org/wiki/images/0/00/Draft_Wire.png) [Wire](http://www.freecadweb.org/wiki/index.php?title=Draft_Wire) | Draws a line made of multiple line segments (polyline) |
| ![icon](http://www.freecadweb.org/wiki/images/1/10/Draft_Circle.png) [Circle](http://www.freecadweb.org/wiki/index.php?title=Draft_Circle) | Draws a circle from center and radius | ![icon](http://www.freecadweb.org/wiki/images/a/a8/Draft_Arc.png) [Arc](http://www.freecadweb.org/wiki/index.php?title=Draft_Arc) | Draws an arc segment from center, radius, start angle and end angle |
| ![icon](http://www.freecadweb.org/wiki/images/thumb/1/13/Draft_Ellipse.png/32px-Draft_Ellipse.png)[Ellipse](http://www.freecadweb.org/wiki/index.php?title=Draft_Ellipse) | Draws an ellipse from two corner points | ![icon](http://www.freecadweb.org/wiki/images/8/8e/Draft_Polygon.png) [Polygon](http://www.freecadweb.org/wiki/index.php?title=Draft_Polygon) | Draws a regular polygon from a center and a radius |
| ![icon](http://www.freecadweb.org/wiki/images/1/14/Draft_Rectangle.png) [Rectangle](http://www.freecadweb.org/wiki/index.php?title=Draft_Rectangle) | Draws a rectangle from 2 opposite points | ![icon](http://www.freecadweb.org/wiki/images/9/9f/Draft_Text.png) [Text](http://www.freecadweb.org/wiki/index.php?title=Draft_Text) | Draws a multi-line text annotation |
| ![icon](http://www.freecadweb.org/wiki/images/b/b0/Draft_Dimension.png) [Dimension](http://www.freecadweb.org/wiki/index.php?title=Draft_Dimension) | Draws a dimension annotation | ![icon](http://www.freecadweb.org/wiki/images/a/af/Draft_BSpline.png) [BSpline](http://www.freecadweb.org/wiki/index.php?title=Draft_BSpline) | Draws a B-Spline from a series of points |
| ![icon](http://www.freecadweb.org/wiki/images/thumb/c/c5/Draft_Point.png/32px-Draft_Point.png) [Point](http://www.freecadweb.org/wiki/index.php?title=Draft_Point) | Inserts a single point | ![icon](http://www.freecadweb.org/wiki/images/f/f7/Draft_ShapeString.png) [ShapeString](http://www.freecadweb.org/wiki/index.php?title=Draft_ShapeString) | The ShapeString tool inserts a compound shape representing a text string at a given point in the current document |
| ![icon](http://www.freecadweb.org/wiki/images/thumb/9/93/Draft_Facebinder.png/32px-Draft_Facebinder.png) [Facebinder](http://www.freecadweb.org/wiki/index.php?title=Draft_Facebinder) | Creates a new object from selected faces on existing objects | ![icon](http://www.freecadweb.org/wiki/images/thumb/3/34/Draft_BezCurve.png/32px-Draft_BezCurve.png) [BezierCurve](http://www.freecadweb.org/wiki/index.php?title=Draft_BezCurve) | Draws a Bezier curve from a series of points | 
| ![icon](http://www.freecadweb.org/wiki/images/c/c5/Draft_Move.png) [Move](http://www.freecadweb.org/wiki/index.php?title=Draft_Move) | Moves or copies objects from one location to another | ![icon](http://www.freecadweb.org/wiki/images/5/5a/Draft_Rotate.png) [Rotate](http://www.freecadweb.org/wiki/index.php?title=Draft_Rotate) | Rotates objects by a certain angle around a point | 
| ![icon](http://www.freecadweb.org/wiki/images/e/eb/Draft_Offset.png) [Offset](http://www.freecadweb.org/wiki/index.php?title=Draft_Offset) | Offsets an object to a certain distance | ![icon](http://www.freecadweb.org/wiki/images/e/e7/Draft_Trimex.png) [Trimex](http://www.freecadweb.org/wiki/index.php?title=Draft_Trimex) | Trims, extends or extrudes an object | 
| ![icon](http://www.freecadweb.org/wiki/images/b/be/Draft_Upgrade.png) [Upgrade](http://www.freecadweb.org/wiki/index.php?title=Draft_Upgrade) | Turns or joins objects into a higher-level object | ![icon](http://www.freecadweb.org/wiki/images/8/86/Draft_Downgrade.png) [Downgrade](http://www.freecadweb.org/wiki/index.php?title=Draft_Downgrade) | Turns or separtes objects into lower-level objects |
| ![icon](http://www.freecadweb.org/wiki/images/c/c9/Draft_Scale.png) [Scale](http://www.freecadweb.org/wiki/index.php?title=Draft_Scale) | Scales objects in relation to a point | ![icon](http://www.freecadweb.org/wiki/images/9/9f/Draft_Shape2DView.png) [Shape2DView](http://www.freecadweb.org/wiki/index.php?title=Draft_Shape2DView) | Creates a 2D object which is a flattened view of another object |
| ![icon](http://www.freecadweb.org/wiki/images/thumb/b/b2/Draft_Draft2Sketch.png/32px-Draft_Draft2Sketch.png) [Draft2Sketch](http://www.freecadweb.org/wiki/index.php?title=Draft_Draft2Sketch) | Converts a Draft object to a Sketch and vice-versa | ![icon](http://www.freecadweb.org/wiki/images/thumb/c/c8/Draft_Array.png/32px-Draft_Array.png) [Array](http://www.freecadweb.org/wiki/index.php?title=Draft_Array) | Creates a polar or rectangular array from an object |
| ![icon](http://www.freecadweb.org/wiki/images/thumb/c/c1/Draft_PathArray.png/32px-Draft_PathArray.png) [PathArray](http://www.freecadweb.org/wiki/index.php?title=Draft_PathArray) | Creates an array from an object by placing copies along a path | ![icon](http://www.freecadweb.org/wiki/images/thumb/3/39/Draft_Clone.png/32px-Draft_Clone.png) [Clone](http://www.freecadweb.org/wiki/index.php?title=Draft_Clone) | Creates linked copies of objects |
| ![icon](http://www.freecadweb.org/wiki/images/thumb/3/3f/Draft_Mirror.png/32px-Draft_Mirror.png) [Mirror](http://www.freecadweb.org/wiki/index.php?title=Draft_Mirror) | Mirrors objects across a line |



**Read more**

* The complete list of workbenches: http://www.freecadweb.org/wiki/index.php?title=Workbenches
* The draft workbench: http://www.freecadweb.org/wiki/index.php?title=Draft_Module
