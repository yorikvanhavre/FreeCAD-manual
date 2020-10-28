## All workbenches at a glance



One of the biggest difficulty for new users of FreeCAD is to know in which workbench to find a specific tool. The table below will give you an overview of the most important workbenches and their tools. It does not cover all the tools nor all the workbenches available in FreeCAD, the idea here is only to provide you a general map. Refer to the [workbench](http://wiki.freecadweb.org/Workbenches) page in the FreeCAD documentation for a more complete list. Browse each specific workbench page for a list of the their tools with a short description.

Four workbenches are also designed to work in pairs, and one of them is fully included into the other: Arch contains all the Draft tools, and PartDesign all the Sketcher tools. However, for clarity, they are separated below.



### Part

The <img src="../images/icons/Workbench_Part.svg" style="width:24px;" />[Part workbench](https://wiki.freecadweb.org/Part_Workbench) provides basic tools for working with solid geometry: primitives, such as cube and sphere, and simple geometric operations and boolean operations. Being the main anchor point with [OpenCasCade](https://en.wikipedia.org/wiki/Open_Cascade_Technology), the Part workbench provides the foundation of FreeCAD's geometry system, and almost all other workbenches produce Part-based geometry.

| Tool | Description | Tool | Description |
| ---- | ----------- | ---- | ----------- |
| ![icon](../images/icons/32px-Part_Box.png) [Box](http://wiki.freecadweb.org/Part_Box) | Draws a box | ![icon](../images/icons/32px-Part_Cone.png) [Cone](http://wiki.freecadweb.org/Part_Cone) | Draws a cone |
| ![icon](../images/icons/32px-Part_Cylinder.png) [Cylinder](http://wiki.freecadweb.org/Part_Cylinder) | Draws a cylinder | ![icon](../images/icons/32px-Part_Sphere.png) [Sphere](http://wiki.freecadweb.org/Part_Sphere) | Draws a sphere |
| ![icon](../images/icons/32px-Part_Torus.png) [Torus](http://wiki.freecadweb.org/Part_Torus) | Draws a torus (ring) | ![icon](../images/icons/32px-Part_CreatePrimitives.png) [Create Primitives](http://wiki.freecadweb.org/Part_CreatePrimitives) | Creates various other parametric geometric primitives such as lines or planes |
| ![icon](../images/icons/32px-Part_Shapebuilder.png) [Shape Builder](http://wiki.freecadweb.org/Part_Shapebuilder) | Create other shapes from edges or faces of existing objects | ![icon](../images/icons/32px-Part_Fuse.png) [Fuse](http://wiki.freecadweb.org/Part_Fuse) | Fuses (unions) two objects |
| ![icon](../images/icons/32px-Part_Common.png) [Common](http://wiki.freecadweb.org/Part_Common) | Extracts the common (intersection) part of two objects | ![icon](../images/icons/32px-Part_Cut.png) [Cut](http://wiki.freecadweb.org/Part_Cut) | Cuts (subtracts) one object from another |
| ![icon](../images/icons/32px-Part_Thickness.png) [Thickness](http://wiki.freecadweb.org/Part_Thickness) | Assign a thickness to the faces of a shape | ![icon](../images/icons/32px-Part_Extrude.png) [Extrude](http://wiki.freecadweb.org/Part_Extrude) | Extrudes planar faces of an object |
| ![icon](../images/icons/32px-Part_Fillet.png) [Fillet](http://wiki.freecadweb.org/Part_Fillet) | Fillets (rounds) edges of an object | ![icon](../images/icons/32px-Part_Revolve.png) [Revolve](http://wiki.freecadweb.org/Part_Revolve) | Creates a solid by revolving another object (not solid) around an axis |
| ![icon](../images/icons/32px-Part_Section.png) [Section](http://wiki.freecadweb.org/Part_Section) | Creates a section by intersecting an object with a section plane | ![icon](../images/icons/32px-Part_SectionCross.png) [Section Cross](http://wiki.freecadweb.org/Part_SectionCross) | Creates multiple cross sections along an object |
| ![icon](../images/icons/32px-Part_Chamfer.png) [Chamfer](http://wiki.freecadweb.org/Part_Chamfer) | Chamfers edges of an object | <img src="../images/icons/Part_Mirror.png" alt="icon" style="width:32px" /> [Mirror](http://wiki.freecadweb.org/Part_Mirror) | Mirrors the selected object on a given mirror plane |
| <img src="../images/icons/Part_RuledSurface.png" alt="icon" style="width:32px;" /> [Ruled Surface](http://wiki.freecadweb.org/Part_RuledSurface) | Create a ruled surface between selected curves | ![icon](../images/icons/32px-Part_Sweep.png) [Sweep](http://wiki.freecadweb.org/Part_Sweep) | Sweeps one or more profiles along a path |
| ![icon](../images/icons/32px-Part_Loft.png) [Loft](http://wiki.freecadweb.org/Part_Loft) | Lofts from one profile to another | ![icon](../images/icons/32px-Part_Offset.png) [Offset](http://wiki.freecadweb.org/Part_Offset) | Creates a scaled copy of the original object |



### Draft

The <img src="../images/icons/Workbench_Draft.svg" style="width:24px;" />[Draft workbench](https://wiki.freecadweb.org/Draft_Module) provides tools to do basic 2D CAD drafting tasks: lines, circles, etc... and a series of generic handy tools such as move, rotate or scale. It also provides several drawing aids, such as grid and snapping. It is principally meant to draw the guidelines for Arch objects, but also serves as FreeCAD's "swiss army knife".

| Tool | Description | Tool | Description |
| ---- | ----------- | ---- | ----------- |
| <img src="../images/icons/Draft_Line.png" alt="icon" style="width:32px;" /> [Line](http://wiki.freecadweb.org/Draft_Line) | Draws a line segment between 2 points | <img src="../images/icons/Draft_Wire.png" alt="icon" style="width:32px;" /> [Wire](http://wiki.freecadweb.org/Draft_Wire) | Draws a line made of multiple line segments (polyline) |
| <img src="../images/icons/Draft_Circle.png" alt="icon" style="width:32px;" /> [Circle](http://wiki.freecadweb.org/Draft_Circle) | Draws a circle from center and radius | <img src="../images/icons/Draft_Arc.png" alt="icon" style="width:32px;" /> [Arc](http://wiki.freecadweb.org/Draft_Arc) | Draws an arc segment from center, radius, start angle and end angle |
| ![icon](../images/icons/32px-Draft_Ellipse.png)[Ellipse](http://wiki.freecadweb.org/Draft_Ellipse) | Draws an ellipse from two corner points | <img src="../images/icons/Draft_Polygon.png" alt="icon" style="width:32px;" /> [Polygon](http://wiki.freecadweb.org/Draft_Polygon) | Draws a regular polygon from a center and a radius |
| <img src="../images/icons/Draft_Rectangle.png" alt="icon" style="width:32px;" /> [Rectangle](http://wiki.freecadweb.org/Draft_Rectangle) | Draws a rectangle from 2 opposite points | <img src="../images/icons/Draft_Text.png" alt="icon" style="width:32px;" /> [Text](http://wiki.freecadweb.org/Draft_Text) | Draws a multi-line text annotation |
| <img src="../images/icons/Draft_Dimension.png" alt="icon" style="width:32px;" /> [Dimension](http://wiki.freecadweb.org/Draft_Dimension) | Draws a dimension annotation | <img src="../images/icons/Draft_BSpline.png" alt="icon" style="width:32px;" /> [BSpline](http://wiki.freecadweb.org/Draft_BSpline) | Draws a B-Spline from a series of points |
| ![icon](../images/icons/32px-Draft_Point.png) [Point](http://wiki.freecadweb.org/Draft_Point) | Inserts a single point | <img src="../images/icons/Draft_ShapeString.png" alt="icon" style="width:32px;" /> [Shape String](http://wiki.freecadweb.org/Draft_ShapeString) | The ShapeString tool inserts a compound shape representing a text string at a given point in the current document |
| <img src="../images/icons/Draft_Move.png" alt="icon" style="width:32px;" /> [Move](http://wiki.freecadweb.org/Draft_Move) | Moves or copies objects from one location to another | <img src="../images/icons/Draft_Rotate.png" alt="icon" style="width:32px;" /> [Rotate](http://wiki.freecadweb.org/Draft_Rotate) | Rotates objects by a certain angle around a point |
| <img src="../images/icons/Draft_Offset.png" alt="icon" style="width:32px;" /> [Offset](http://wiki.freecadweb.org/Draft_Offset) | Offsets an object to a certain distance | <img src="../images/icons/Draft_Trimex.png" alt="icon" style="width:32px;" /> [Trimex](http://wiki.freecadweb.org/Draft_Trimex) | Trims, extends or extrudes an object |
| <img src="../images/icons/Draft_Upgrade.png" alt="icon" style="width:32px;" /> [Upgrade](http://wiki.freecadweb.org/Draft_Upgrade) | Turns or joins objects into a higher-level object | <img src="../images/icons/Draft_Downgrade.png" alt="icon" style="width:32px;" /> [Downgrade](http://wiki.freecadweb.org/Draft_Downgrade) | Turns or separates objects into lower-level objects |
| <img src="../images/icons/Draft_Scale.png" alt="icon" style="width:32px;" /> [Scale](http://wiki.freecadweb.org/Draft_Scale) | Scales objects in relation to a point | <img src="../images/icons/Draft_Shape2DView.png" alt="icon" style="width:32px;" /> [Shape2D View](http://wiki.freecadweb.org/Draft_Shape2DView) | Creates a 2D object which is a flattened view of another object |
| ![icon](../images/icons/32px-Draft_Draft2Sketch.png) [Draft2Sketch](http://wiki.freecadweb.org/Draft_Draft2Sketch) | Converts a Draft object to a Sketch and vice-versa | ![icon](../images/icons/32px-Draft_Array.png) [Array](http://wiki.freecadweb.org/Draft_Array) | Creates a polar or rectangular array from an object |
| ![icon](../images/icons/32px-Draft_PathArray.png) [PathArray](http://wiki.freecadweb.org/Draft_PathArray) | Creates an array from an object by placing copies along a path | ![icon](../images/icons/32px-Draft_Clone.png) [Clone](http://wiki.freecadweb.org/Draft_Clone) | Creates linked copies of objects |
| ![icon](../images/icons/32px-Draft_Mirror.png) [Mirror](http://wiki.freecadweb.org/Draft_Mirror) | Mirrors objects across a line |||



### Sketcher

The <img src="../images/icons/Workbench_Sketcher.svg" style="width:24px;" />[Sketcher workbench](https://wiki.freecadweb.org/Sketcher_Workbench) contains tools to build and edit complex 2D objects, called sketches. The geometry inside these sketches can be precisely positioned and bound by the use of constraints. They are meant primarily to be the building blocks of PartDesign geometry, but are useful everywhere in FreeCAD.

| Tool | Description | Tool | Description |
| ---- | ----------- | ---- | ----------- |
| ![icon](../images/icons/32px-Sketcher_CreatePoint.png) [Point](http://wiki.freecadweb.org/Sketcher_Point) | Draws a point | ![icon](../images/icons/32px-Sketcher_Line.png) [Line by 2 points](http://wiki.freecadweb.org/Sketcher_Line) | Draws a line segment from 2 points |
| ![icon](../images/icons/32px-Sketcher_Arc.png) [Arc](http://wiki.freecadweb.org/Sketcher_Arc) | Draws an arc segment from center, radius, start angle and end angle | ![icon](../images/icons/32px-Sketcher_CreateArc3Point.png) [Arc by 3 points](http://wiki.freecadweb.org/Sketcher_Arc3Point) | Draws an arc segment from two endpoints and another point on the circumference |
| ![icon](../images/icons/32px-Sketcher_Circle.png) [Circle](http://wiki.freecadweb.org/Sketcher_Circle) | Draws a circle from center and radius | ![icon](../images/icons/32px-Sketcher_CreateCircle3Point.png) [Circle by 3 points](http://wiki.freecadweb.org/Sketcher_Circle3Point) | Draws a circle from three points on the circumference |
| ![icon](../images/icons/32px-Sketcher_CreateEllipse.png) [Ellipse by center](http://wiki.freecadweb.org/Sketcher_Ellipse) | Draws an ellipse by center point, major radius point and minor radius point | ![icon](../images/icons/32px-Sketcher_CreateEllipse3Point.png) [Ellipse by 3 points](http://wiki.freecadweb.org/Sketcher_Ellipse_by_3_Points) | Draws an ellipse by major diameter (2 points) and minor radius point |
| ![icon](../images/icons/32px-Sketcher_CreateArcOfEllipse.png) [Arc of ellipse](http://wiki.freecadweb.org/Sketcher_Arc_of_Ellipse) | Draws an arc of ellipse by center point, major radius point, starting point and ending point | ![icon](../images/icons/32px-Sketcher_CreatePolyline.png) [Polyline](http://wiki.freecadweb.org/Sketcher_Polyline) | Draws a line made of multiple line segments. Several drawing modes available |
| ![icon](../images/icons/32px-Sketcher_CreateRectangle.png) [Rectangle](http://wiki.freecadweb.org/Sketcher_Rectangle) | Draws a rectangle from 2 opposite points | ![icon](../images/icons/32px-Sketcher_CreateTriangle.png) [Triangle](http://wiki.freecadweb.org/Sketcher_Triangle) | Draws a regular triangle inscribed in a construction geometry circle |
| ![icon](../images/icons/32px-Sketcher_CreateSquare.png) [Square](http://wiki.freecadweb.org/Sketcher_Square) | Draws a regular square inscribed in a construction geometry circle | ![icon](../images/icons/32px-Sketcher_CreatePentagon.png) [Pentagon](http://wiki.freecadweb.org/Sketcher_Pentagon) | Draws a regular pentagon inscribed in a construction geometry circle |
| ![icon](../images/icons/32px-Sketcher_CreateHexagon.png) [Hexagon](http://wiki.freecadweb.org/Sketcher_Hexagon) | Draws a regular hexagon inscribed in a construction geometry circle | ![icon](../images/icons/32px-Sketcher_CreateHeptagon.png) [Heptagon](http://wiki.freecadweb.org/Sketcher_Heptagon) | Draws a regular heptagon inscribed in a construction geometry circle |
| ![icon](../images/icons/32px-Sketcher_CreateOctagon.png) [Octagon](http://wiki.freecadweb.org/Sketcher_Octagon) | Draws a regular octagon inscribed in a construction geometry circle | ![icon](../images/icons/32px-Sketcher_CreateSlot.png) [Slot](http://wiki.freecadweb.org/Sketcher_Slot) | Draws an oval by selecting the center of one semicircle and an endpoint of the other semicircle |
| ![icon](../images/icons/32px-Sketcher_CreateFillet.png) [Fillet](http://wiki.freecadweb.org/Sketcher_Fillet) | Makes a fillet between two lines joined at one point | ![icon](../images/icons/32px-Sketcher_Trimming.png) [Trim](http://wiki.freecadweb.org/Sketcher_Trimming) | Trims a line, circle or arc with respect to a clicked point |
| ![icon](../images/icons/32px-Sketcher_External.png) [External Geometry](http://wiki.freecadweb.org/Sketcher_External) | Creates an edge linked to external geometry | ![icon](../images/icons/32px-Sketcher_AlterConstruction.png) [Construction Mode](http://wiki.freecadweb.org/Sketcher_ConstructionMode) | Toggles an element to/from construction mode. A construction object will not be used in a 3D geometry operation and is only visible while editing the Sketch that contains it |
| <img src="../images/icons/Sketcher_ConstrainCoincident.svg" alt="icon" style="width:32px;" /> [Coincident constraint](http://wiki.freecadweb.org/Constraint_PointOnPoint) | Affixes a point onto (coincident with) one or more other points. | <img src="../images/icons/Sketcher_ConstrainPointOnObject.svg" alt="icon" style="width:32px;" /> [Point On Object constraint](http://wiki.freecadweb.org/Constraint_PointOnObject) | Affixes a point onto another object such as a line, arc, or axis. |
| ![icon](../images/icons/32px-Constraint_Vertical.png) [Vertical constraint](http://wiki.freecadweb.org/Constraint_Vertical) | Constrains the selected lines or polyline elements to a true vertical orientation. More than one object can be selected before applying this constraint. | ![icon](../images/icons/32px-Constraint_Horizontal.png) [Horizontal constraint](http://wiki.freecadweb.org/Constraint_Horizontal) | Constrains the selected lines or polyline elements to a true horizontal orientation. More than one object can be selected before applying this constraint. |
| <img src="../images/icons/Sketcher_ConstrainParallel.svg" alt="icon" style="width:32px;" /> [Parallel constraint](http://wiki.freecadweb.org/Constraint_Parallel) | Constrains two or more lines parallel to one another. | <img src="../images/icons/Sketcher_ConstrainPerpendicular.svg" alt="icon" style="width:32px;" /> [Perpendicular constraint](http://wiki.freecadweb.org/Constraint_Perpendicular) | Constrains two lines perpendicular to one another, or constrains a line perpendicular to an arc endpoint. |
| ![icon](../images/icons/32px-Constraint_Tangent.png) [Tangent constraint](http://wiki.freecadweb.org/Constraint_Tangent) | Creates a tangent constraint between two selected entities, or a co-linear constraint between two line segments. | <img src="../images/icons/Sketcher_ConstrainEqual.svg" alt="icon" style="width:32px;" /> [Equal Length constraint](http://wiki.freecadweb.org/Constraint_EqualLength) | Constrains two selected entities equal to one another.  If used on circles or arcs their radii will be set equal. |
| <img src="../images/icons/Sketcher_ConstrainSymmetric.svg" alt="icon" style="width:32px;" /> [Symmetric constraint](http://wiki.freecadweb.org/Constraint_Symmetric) | Constrains two points symmetrically about a line, or constrains the first two selected points symmetrically about a third selected point. | ![icon](../images/icons/32px-Sketcher_ConstrainLock.png) [Lock constraint](http://wiki.freecadweb.org/Constraint_Lock) | Constrains the selected item by setting vertical and horizontal distances relative to the origin, thereby locking the location of that item |
| <img src="../images/icons/Sketcher_ConstrainDistanceX.svg" alt="icon" style="width:32px;" /> [Horizontal Distance constraint](http://wiki.freecadweb.org/Constraint_HorizontalDistance) | Fixes the horizontal distance between two points or line endpoints. If only one item is selected, the distance is set to the origin.  | <img src="../images/icons/Sketcher_ConstrainDistanceY.svg" alt="icon" style="width:32px;" /> [Vertical Distance constraint](http://wiki.freecadweb.org/Constraint_VerticalDistance) | Fixes the vertical distance between 2 points or line endpoints. If only one item is selected, the distance is set to the origin. |
| <img src="../images/icons/Sketcher_ConstrainDistance.svg" alt="icon" style="width:32px;" /> [Length constraint](http://wiki.freecadweb.org/Constraint_Length) | Defines the distance of a selected line by constraining its length, or defines the distance between two points by constraining the distance between them.  | <img src="../images/icons/Sketcher_ConstrainRadius.svg" alt="icon" style="width:32px;" /> [Radius constraint](http://wiki.freecadweb.org/Constraint_Radius) | Defines the radius of a selected arc or circle by constraining the radius. |
| ![icon](../images/icons/32px-Constraint_InternalAngle.png) [Internal Angle constraint](http://wiki.freecadweb.org/Constraint_InternalAngle) | Defines the internal angle between two selected lines. | ![icon](../images/icons/32px-Constraint_SnellsLaw.png) [Snell's Law constraint](http://wiki.freecadweb.org/Constraint_SnellsLaw) | Constrains two lines to obey a refraction law to simulate the light going through an interface |



### Part Design

The <img src="../images/icons/Workbench_PartDesign.svg" style="width:24px;" /> [Part Design workbench](https://wiki.freecadweb.org/PartDesign_Workbench) contains advanced tools to build solid parts. It also contains all the tools from the sketcher. Since it can only produces solid shapes (the rule number one of Part Design), it is the main workbench to use when designing pieces (parts) to be manufactured or 3D-printed, as you will always obtain a printable object.

| Tool | Description | Tool | Description |
| ---- | ----------- | ---- | ----------- |
| ![icon](../images/icons/32px-PartDesign_Pad.png) [Pad](http://wiki.freecadweb.org/PartDesign_Pad) | Extrudes a solid object from a selected sketch | ![icon](../images/icons/32px-PartDesign_Pocket.png) [Pocket](http://wiki.freecadweb.org/PartDesign_Pocket) | Creates a pocket from a selected sketch. The sketch must be mapped to an existing solid object's face |
| ![icon](../images/icons/32px-PartDesign_Revolution.png) [Revolution](http://wiki.freecadweb.org/PartDesign_Revolution) | Creates a solid by revolving a sketch around an axis | ![icon](../images/icons/32px-PartDesign_Groove.png) [Groove](http://wiki.freecadweb.org/PartDesign_Groove) | Creates a groove by revolving a sketch around an axis |
| ![icon](../images/icons/32px-PartDesign_Fillet.png) [Fillet](http://wiki.freecadweb.org/PartDesign_Fillet) | Fillets (rounds) edges of an object | ![icon](../images/icons/32px-PartDesign_Chamfer.png) [Chamfer](http://wiki.freecadweb.org/PartDesign_Chamfer) | Chamfers edges of an object |
| ![icon](../images/icons/32px-PartDesign_Draft.png) [Draft](http://wiki.freecadweb.org/PartDesign_Draft) | Applies angular draft to faces of an object | ![icon](../images/icons/32px-PartDesign_Mirrored.png) [Mirrored](http://wiki.freecadweb.org/PartDesign_Mirrored) | Mirrors features on a plane or face |
| ![icon](../images/icons/32px-PartDesign_LinearPattern.png) [Linear Pattern](http://wiki.freecadweb.org/PartDesign_LinearPattern) | Creates a linear pattern of features | ![icon](../images/icons/32px-PartDesign_PolarPattern.png) [Polar Pattern](http://wiki.freecadweb.org/PartDesign_PolarPattern) | Creates a polar pattern of features |
| ![icon](../images/icons/32px-PartDesign_Scaled.png) [Scaled](http://wiki.freecadweb.org/PartDesign_Scaled) | Scales features to a different size | ![icon](../images/icons/32px-PartDesign_MultiTransform.png) [MultiTransform](http://wiki.freecadweb.org/PartDesign_MultiTransform) | Allows creating a pattern with any combination of the other transformations |
| ![icon](../images/icons/32px-PartDesign_WizardShaft.png) [Shaft wizard](http://wiki.freecadweb.org/PartDesign_WizardShaft) | Generates a shaft from a table of values and allows to analyze forces and moments | ![icon](../images/icons/32px-PartDesign_InvoluteGear.png) [Involute Gear wizard](http://wiki.freecadweb.org/PartDesign_InvoluteGear) | Allows you to create several types of gears |



### Arch

The <img src="../images/icons/Workbench_Arch.svg" style="width:24px;" />[Arch workbench](https://wiki.freecadweb.org/Arch_Module) contains tools to work with [BIM](https://en.wikipedia.org/wiki/Building_information_modeling) (*Building Information Modeling*) projects (civil engineering and architecture). It also contains all the tools from the Draft workbench. The main use of the Arch Workbench is to create BIM objects or give BIM attributes to objects built with other workbenches, in order to export them to [IFC](https://en.wikipedia.org/wiki/Industry_Foundation_Classes).

| Tool | Description | Tool | Description |
| ---- | ----------- | ---- | ----------- |
| ![icon](../images/icons/32px-Arch_Wall.png) [Wall](http://wiki.freecadweb.org/Arch_Wall) | Creates a wall from scratch or using a selected object as a base | <img src="../images/icons/Arch_Structure.png" alt="icon" style="width:32px;" /> [Structure](http://wiki.freecadweb.org/Arch_Structure) | Creates a structural element from scratch or using a selected object as a base |
| ![icon](../images/icons/32px-Arch_Rebar.png) [Reinforcement Bar](http://wiki.freecadweb.org/Arch_Rebar) | Creates a reinforcement bar in a selected structural element | <img src="../images/icons/Arch_Floor.png" alt="icon" style="width:32px;" /> [Floor](http://wiki.freecadweb.org/Arch_Floor) | Creates a floor including selected objects |
| <img src="../images/icons/Arch_Building.png" alt="icon" style="width:32px;" /> [Building](http://wiki.freecadweb.org/Arch_Building) | Creates a building including selected objects | <img src="../images/icons/Arch_Site.png" alt="icon" style="width:32px;" /> [Site](http://wiki.freecadweb.org/Arch_Site) | Creates a site including selected objects |
| ![icon](../images/icons/32px-Arch_Window.png) [Window](http://wiki.freecadweb.org/Arch_Window) | Creates a window using a selected object as a base | ![icon](../images/icons/32px-Arch_SectionPlane.png) [Section Plane](http://wiki.freecadweb.org/Arch_SectionPlane) | Adds a section plane object to the document |
| ![icon](../images/icons/32px-Arch_Axis.png) [Axes](http://wiki.freecadweb.org/Arch_Axis) | Adds an axes system to the document | ![icon](../images/icons/32px-Arch_Roof.png) [Roof](http://wiki.freecadweb.org/Arch_Roof) | Creates a sloped roof from a selected face |
| ![icon](../images/icons/32px-Arch_Space.png) [Space](http://wiki.freecadweb.org/Arch_Space) | Creates a space object in the document | ![icon](../images/icons/32px-Arch_Stairs.png) [Stairs](http://wiki.freecadweb.org/Arch_Stairs) | Creates a stairs object in the document |
| ![icon](../images/icons/32px-Arch_Panel.png) [Panel](http://wiki.freecadweb.org/Arch_Panel) | Creates a panel object from a selected 2D object | ![icon](../images/icons/32px-Arch_Frame.png) [Frame](http://wiki.freecadweb.org/Arch_Frame) | Creates a frame object from a selected layout |
| ![icon](../images/icons/32px-Arch_Equipment.png) [Equipment](http://wiki.freecadweb.org/Arch_Equipment) | Creates an equipment or furniture object | ![icon](../images/icons/32px-Arch_SetMaterial.png) [Set Material](http://wiki.freecadweb.org/Arch_SetMaterial) | Attributes a material to selected objects |
| ![icon](../images/icons/32px-Arch_Schedule.png) [Schedule](http://wiki.freecadweb.org/Arch_Schedule) | Creates different types of schedules | ![icon](../images/icons/32px-Arch_CutPlane.png) [Cut Plane](http://wiki.freecadweb.org/Arch_CutPlane) | Cut an object according to a plan. |
| <img src="../images/icons/Arch_Add.png" alt="icon" style="width:32px;" /> [Add Component](http://wiki.freecadweb.org/Arch_Add) | Adds objects to a component | <img src="../images/icons/Arch_Remove.png" alt="icon" style="width:32px;" /> [Remove Component](http://wiki.freecadweb.org/Arch_Remove) | Subtracts or removes objects from a component |



### TechDraw

The <img src="../images/icons/Workbench_TechDraw.svg" style="width:24px;" /> [TechDraw workbench](https://wiki.freecadweb.org/TechDraw_Module) handles the creation and manipulation of 2D drawing sheets, used for displaying views of your 3D work in 2D. You can then add additional features like annotations, dimensions, symbols or hatching on those views. These sheets can then be printed or exported to SVG, DXF or PDF files.

| Tool | Description | Tool | Description |
| ---- | ----------- | ---- | ----------- |
| <img src="../images/icons/TechDraw_PageDefault.svg" alt="icon" style="width:32px;" /> [Page](https://wiki.freecadweb.org/TechDraw_PageDefault) | Creates a new page using a default template | <img src="../images/icons/TechDraw_View.svg" style="width:32px" /> [Object view](https://wiki.freecadweb.org/TechDraw_View) | Inserts a 2D projection view of an object |||
| <img src="../images/icons/TechDraw_ProjectionGroup.svg" style="width:32px" /> [Projection group](https://wiki.freecadweb.org/TechDraw_ProjectionGroup) | Creates many views of an object from multiple directions | <img src="../images/icons/TechDraw_SectionView.svg" style="width:32px" /> [Section view](https://wiki.freecadweb.org/TechDraw_SectionView) | Inserts a cross-section view of an object view |||
| <img src="../images/icons/TechDraw_DetailView.svg" style="width:32px" /> [Detail view](https://wiki.freecadweb.org/TechDraw_DetailView) | Inserts a view of a portion of an object view | <img src="../images/icons/TechDraw_DraftView.svg" style="width:32px" /> [Draft View](https://wiki.freecadweb.org/TechDraw_DraftView) | inserts a view of a [Draft](https://wiki.freecadweb.org/Draft_Workbench) object |||
| <img src="../images/icons/TechDraw_ArchView.svg" style="width:32px" /> [Section plane view](https://wiki.freecadweb.org/TechDraw_ArchView) | inserts a view of an [Arch section plane](https://wiki.freecadweb.org/Arch_SectionPlane) | <img src="../images/icons/TechDraw_SpreadsheetView.svg" style="width:32px" /> [Spreadsheet view](https://wiki.freecadweb.org/TechDraw_SpreadsheetView) | Inserts a view of a [spreadsheet](https://wiki.freecadweb.org/Spreadsheet_Workbench) |||
| <img src="../images/icons/TechDraw_ClipGroup.svg" style="width:32px" /> [Clip group](https://wiki.freecadweb.org/TechDraw_ClipGroup) | Creates a clip group | <img src="../images/icons/TechDraw_ClipGroupAdd.svg" style="width:32px" /> [Add to clip group](https://wiki.freecadweb.org/TechDraw_ClipGroupAdd) | Adds a view to a clip group |||
| <img src="../images/icons/TechDraw_ClipGroupRemove.svg" style="width:32px" /> [Remove from clip group](https://wiki.freecadweb.org/TechDraw_ClipGroupRemove) | Removes a view from a clip group | <img src="../images/icons/TechDraw_Dimension_Length.svg" style="width:32px" /> [Length dimension](https://wiki.freecadweb.org/TechDraw_Dimension_Length) | Adds a length dimension |||
| <img src="../images/icons/TechDraw_Dimension_Horizontal.svg" style="width:32px" /> [Horizontal dimension](https://wiki.freecadweb.org/TechDraw_Dimension_Horizontal) | Adds a horizontal length dimension | <img src="../images/icons/TechDraw_Dimension_Vertical.svg" style="width:32px" /> [Vertical dimension](https://wiki.freecadweb.org/TechDraw_Dimension_Vertical) | Adds a vertical length dimension |||
| <img src="../images/icons/TechDraw_Dimension_Radius.svg" style="width:32px" /> [Radius dimension](https://wiki.freecadweb.org/TechDraw_Dimension_Radius) | Adds a radius dimension to a circle or circular arc | <img src="../images/icons/TechDraw_Dimension_Diameter.svg" style="width:32px" /> [Diameter dimension](https://wiki.freecadweb.org/TechDraw_Dimension_Diameter) | Adds a diameter dimension to a circle or a circular arc |||
| <img src="../images/icons/TechDraw_Dimension_Angle.svg" style="width:32px" /> [Angle dimension](https://wiki.freecadweb.org/TechDraw_Dimension_Angle) | Adds an angle dimension between two straight edges | <img src="../images/icons/TechDraw_Dimension_Link.svg" style="width:32px" /> [New Links](https://wiki.freecadweb.org/TechDraw_Dimension_Link) | Links an existing dimension to the 3D geometry |||



### Other built-in workbenches

Many more workbenches are available by default in FreeCAD, among them:

* The <img src="../images/icons/Workbench_Mesh.svg" style="width:24px;" /> [Mesh workbench](http://wiki.freecadweb.org/Mesh_Module) allows to work with [polygon meshes](https://en.wikipedia.org/wiki/Polygon_mesh). Although meshes are not the preferred type of geometry to work with in FreeCAD, because of their lack of precision and support for curves, meshes still have a lot of uses, and are fully supported in FreeCAD. The Mesh Workbench also offers a number of Part-to-Mesh and Mesh-to-Part tools
* The <img src="../images/icons/Workbench_Path.svg" style="width:24px;" /> [Path workbench](https://wiki.freecadweb.org/Path_Workbench) handles [CAM](https://en.wikipedia.org/wiki/Cam) (*Computer-Aided Machining*) operations in FreeCAD. It allows you to define paths to be followed and operations to be performed by [CNC](https://en.wikipedia.org/wiki/Numerical_control) machines in order to cut objects out of a block of material. It also contains useful tools for [3D printing](https://en.wikipedia.org/wiki/3D_printing)
* The <img src="../images/icons/Workbench_Spreadsheet.svg" style="width:24px;" /> [Spreadsheet workbench](http://wiki.freecadweb.org/Spreadsheet_Module) permits the creation and manipulation of spreadsheet data, that can be extracted from FreeCAD models. Spreadsheet cells can also be referenced in many areas of FreeCAD, allowing to use them as master data structures
* The <img src="../images/icons/Workbench_FEM.svg" style="width:24px;" /> [FEM workbench](http://wiki.freecadweb.org/Fem_Workbench) deals with [Finite Elements Analysis](https://en.wikipedia.org/wiki/Finite_element_method), and permits the performing of pre- and post-processing FEM calculations and to display the results graphically



### External workbenches

FreeCAD also features a number of very useful [other workbenches](https://wiki.freecadweb.org/External_workbenches) produced by community members. Although they are not included in a standard FreeCAD installation, they are easy to install right from within FreeCAD with the [Addons manager](https://wiki.freecadweb.org/Addon_Manager) found under menu *Tools*. Among them are:

* The [Fasteners workbench](https://github.com/shaise/FreeCAD_FastenersWB) offers a wide range of ready-to-insert fasteners objects like screws, bolts, rods, washers and nuts. Many options and settings are available
* The [Dodo workbench](https://wiki.freecadweb.org/Dodo_Workbench) offers tools to work with metallic structures such as beams and columns
* The [BIM workbench](https://wiki.freecadweb.org/BIM_Workbench) is an experimental, advanced version of the Arch workbench, with a friendlier interface
* The [Render workbench](https://wiki.freecadweb.org/Render_Workbench) allows to produce rendered images using several external rendering applications such as [Povray](http://povray.org/) or [Luxrender](https://luxcorerender.org/)
* The [Assembly3](https://wiki.freecadweb.org/Assembly3_Workbench) and [Assembly4](https://wiki.freecadweb.org/Assembly4_Workbench) workbenches allow to perform constrained assemblies of parts from other files



-----

**Read more**

* The complete list of workbenches: http://wiki.freecadweb.org/Workbenches
* The Part Workbench: http://wiki.freecadweb.org/Part_Module
* The Draft Workbench: http://wiki.freecadweb.org/Draft_Module
* The Sketcher and Part Design Workbench: http://wiki.freecadweb.org/PartDesign_Workbench
* The Arch Workbench: http://wiki.freecadweb.org/Arch_Module
* The TechDraw Workbench: http://wiki.freecadweb.org/TechDraw_Module
* The FEM Workbench: http://wiki.freecadweb.org/Fem_Workbench
* External FreeCAD workbenches: https://wiki.freecadweb.org/External_workbenches
