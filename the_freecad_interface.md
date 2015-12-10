## The FreeCAD interface

FreeCAD uses the Qt framework to draw and manage its interface. This framework is used in a wide range of
applications, so the FreeCAD interface is very classical and presents no particular difficulty to understand.
Most buttons are standard and will be found where you expect them (File -> Open, Edit -> Paste, etc).
Here is the look of FreeCAD when you open it for the first time, just after installing, showing you the
start center:

![FreeCAD interface screenshot 01](http://www.freecadweb.org/wiki/images/4/49/Freecad-interface-01.jpg)

The start center is a convenient "welcome screen", that shows useful information for newcomers, like the latest
files you have been working on, what's new in the FreeCAD world, or quick info about the most common
workbenches. It will also notify you if a new stable version of FreeCAD is available.

But after a while, or after you did some changes in the preferences, you will much more likely find yourself
directly in one of the other workbenches, with a new document open. Or simply, close the
start page tab and create a new document:

![FreeCAD interface screenshot 02](http://www.freecadweb.org/wiki/images/2/28/Freecad-interface-02.jpg)

### Workbenches

Note that some of the icons have changed between the two above screens. This is where enters the most
important concept used in the FreeCAD interface: Workbenches. Workbenches are group of tools (toolbar
buttons, menus, and other interface controls) that are grouped together by specialty. Think of a workshop 
where you have different people working together: A person who works with metal, another with wood. Each of them
has, in the workshop, a separate table with specific tools for his job. However, they can all work on the
same objects. The same happens in FreeCAD.

The most important control of the FreeCAD interface is the workbench selector, which you use to switch from
one workbench to the other:

![FreeCAD interface screenshot 03](http://www.freecadweb.org/wiki/images/9/94/Freecad-interface-03.jpg)

The workbenches often confuse new users, because it is not always easy to know in which workbench to
look for a specific tool. But they are quick to learn, and after a short while it will feel natural, and
it is a great way to organize the huge number of tools that FreeCAD has to offer.

Later in this manual, you will also find a table showing the contents of all workbenches.

Let's have a better look at the different parts of the interface:

![FreeCAD interface screenshot 04](http://www.freecadweb.org/wiki/images/7/76/Freecad-interface-04.jpg)

* **The 3D view** is the main component of the interface. It can be undocked out of the main window, you can have several views of a same document, or several documents opened at the same time. You can select objects or parts of objects by clicking them, and youcan pan, zoom and rotate the view with the mouse buttons. This will be explained further in the next chapter.
* **The combo view** has two tabs: The Model tab shows you the contents and structure of your document above, and the properties (parameters) of the selected object(s) below. These properties are separated in two categories: Data (properties which concern the geometry itself) and View (properties that affect how the geometry looks like on screen).The Tasks tab will be used automatically by tools when they need your input of to show you some information.
* **The report view** is normally hidden, but it is a good idea to leave it open if something doesn't work the way you expect, because that is where FreeCAD will show you information, warnings or errors.
* **The Python console** is also hidden by default. This is where you can interact with the contents of the document using the [Python language](https://en.wikipedia.org/wiki/Python_%28programming_language%29). Since every action you do on the FreeCAD interface actually executes a piece of python code, having this window open allows you to watch this, and it is a wonderful and easy way to learn some Python on the way, almost without noticing it.

Most of the tools, when needing some action from you, will switch the combo view in Task mode, and use it to display
specific controls, with which you can interact with the tool and make it do what you want:

![FreeCAD interface screenshot 05](http://www.freecadweb.org/wiki/images/4/4f/Freecad-interface-07.jpg)

The task tab will close automatically after you press the OK (or Cancel) button. Most tools will also allow you to 
reopen that task panel, in order to modify the settings, by double-clicking the related object in the combo view.

### Customizing the interface

The interface of FreeCAD is deeply customizable. All panels and toolbars can be moved to different places or
stacked one with another. They can also be closed and reopened when needed from the View menu or by right-clicking
on an empty area of the interface. But there are many more options available, such as creating custom toolbars
with tools from any of the workbenches, or assigning and changing keyboard shortcuts.

These advanced customization options are availabe from the Tools -> Customize menu:

![FreeCAD interface screenshot 05](http://www.freecadweb.org/wiki/images/3/30/Freecad-interface-06.jpg)

**Read more**

* Getting started with FreeCAD: http://www.freecadweb.org/wiki/index.php?title=Getting_started
* Customizing the interface: http://www.freecadweb.org/wiki/index.php?title=Interface_Customization
* Workbenches: http://www.freecadweb.org/wiki/index.php?title=Workbenches
* More about Python: https://www.python.org
