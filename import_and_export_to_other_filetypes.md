## Import and export to other filetypes

FreeCAD can import and export to many filetypes. Here is a list of the most important ones with a
short description of the available features:

| Format | Import | Export | Notes |
| ------ | ------ | ------ | ----- |
| STEP   | Yes    | Yes    | This is the most faithful import/export format available, since it supports solid geometry and NURBS. Use it whenever it is possible. |
| IGES   | Yes    | Yes    | An older solid format, also very well supported. Some older applications don't support Step but have Iges. |
| BREP   | Yes    | Yes    | The native format of [OpenCasCade](https://en.wikipedia.org/wiki/Open_Cascade_Technology), FreeCAD's geometry kernel.  |
| DXF    | Yes    | Yes    | An open format maintained by Autodesk. Since the 3D data inside a DXF file is encoded in proprietary format, FreeCAD can only import/export 2D data to/from this format.|
| DWG    | Yes    | Yes    | The proprietary version of DXF. Requires the installation of the [Teigha File Converter](https://www.opendesign.com/guestfiles) utility. This format suffers from the same limitations as DXF.|
| OBJ    | Yes    | Yes    | A mesh-based format. Can only contain triangulated meshes. All solid and NURBS-based objects of FreeCAD will be converted to mesh on export. An alternative exporter is provided by the Arch workbench, more suited to the export of architectural models.|
| DAE    | Yes    | Yes    | The main import/export format of Sketchup. Can only contain triangulated meshes. All solid and NURBS-based objects of FreeCAD will be converted to mesh on export. |
| STL    | Yes    | Yes    | A mesh-based format, commonly used for 3D printing. Can only contain triangulated meshes. All solid and NURBS-based objects of FreeCAD will be converted to mesh on export. |
| PLY    | Yes    | Yes    | An older mesh-based format. Can only contain triangulated meshes. All solid and NURBS-based objects of FreeCAD will be converted to mesh on export. |
| IFC    | Yes    | Yes    | [Industry Foundation Classes](https://en.wikipedia.org/wiki/Industry_Foundation_Classes). Requires the installation of [IfcOpenShell-python](http://ifcopenshell.org/python.html). The IFC format and its compatibility with other applications is a complex affair, use with care.|
| SVG    | Yes    | Yes    | An excellent, widespread 2D graphics format |
| VRML   | Yes    | Yes    | A rather old mesh-based web format. |
| GCODE  | Yes    | Yes    | FreeCAD can already import and export to/from several flavors of GCode, but only a small number of machines is supported at the moment. |
| CSG    | Yes    | No     | OpenSCAD's CSG format. |

Some of these file formats have options. These can be configured from menu Edit -> Preferences -> Import/export:
![Import/export preferences](http://www.freecadweb.org/wiki/images/4/41/Import_preferences.jpg)

**Read more**

* Working with DXF files in FreeCAD: http://www.freecadweb.org/wiki/index.php?title=Draft_DXF
* Enabling DXF and DWG support: http://www.freecadweb.org/wiki/index.php?title=Dxf_Importer_Install
* Working with SVG files in FreeCAD: http://www.freecadweb.org/wiki/index.php?title=Draft_SVG
* Importing and exporting to IFC: http://www.freecadweb.org/wiki/index.php?title=Arch_IFC
* OpenCasCade: http://www.opencascade.com
* Teigha File Converter: https://www.opendesign.com/guestfiles
* The IFC format: http://www.buildingsmart-tech.org/ifc/IFC4/final/html/index.htm
* IfcOpenShell: http://ifcopenshell.org/
