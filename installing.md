## Installing

FreeCAD uses the [LGPL](https://en.wikipedia.org/wiki/GNU_Lesser_General_Public_License) license, which makes 
you free to download, install, redistribute and use FreeCAD the way you want, regardless of the type of work 
you'll do with it (commercial or non-commercial). You are not bound to any clause or restriction, and the files
you produce with it are fully yours. The only thing that the license prohibits, really, is to claim that you 
programmed FreeCAD yourself!

FreeCAD runs without any difference on Windows, Mac OS and Linux. However, the ways to install it differ slightly
depending on your platform: On Windows and Mac, the FreeCAD community provides precompiled packages
(installers) ready to download, while on Linux, the source code is made available to Linux distributions
maintainers, who are then responsible for packaging FreeCAD for their specific distribution. As a result,
on Linux, you can usually install FreeCAD right from the software manager application.

The official FreeCAD download page for Windows and Mac OS is https://github.com/FreeCAD/FreeCAD/releases

**FreeCAD versions**

The official releases of FreeCAD, that you can find on the page above and in your distribution's software
manager, are stable versions. However, the development of FreeCAD is fast! New features and bug fixes
are added almost every single day. Since it can sometimes take a long time between stable releases, you might
be interested in trying a more bleeding-edge version of FreeCAD. These development versions, or pre-releases,
are uploaded from time to time on the download page above, or, if you are using Ubuntu, the FreeCAD community
also maintains a [PPA](https://launchpad.net/~freecad-maintainers/+archive/ubuntu/freecad-daily) which is 
regularly updated with the most recent changes.

### Installing on Windows

1. Download an installer (.exe) package corresponding to your version of Windows (32bit or 64bit) from  the [download page]( https://github.com/FreeCAD/FreeCAD/release). The FreeCAD installers should work on any windows version.
2. Double-click the downloaded installer.
3. Accept the terms of the LGPL license (this will be one of the few cases where you can really, safely click the "accept" button without reading the text. No hidden clauses):
![FreeCAD installation on windows, step 1](http://www.freecadweb.org/wiki/images/0/05/Freecad-windows-install-01.jpg)
4. You can leave the default path here, or change if you wish:
![FreeCAD installation on windows, step 2](http://www.freecadweb.org/wiki/images/7/73/Freecad-windows-install-02.jpg)
5. No need to set the PYTHONPATH variable, unless you plan to do some advanced python programming, in which case you probably already know what this is for:
![FreeCAD installation on windows, step 3](http://www.freecadweb.org/wiki/images/1/1b/Freecad-windows-install-03.jpg)
6. During the installation, a couple of additional components, which are bundled inside the installer, will be installed too:
![FreeCAD installation on windows, step 4](http://www.freecadweb.org/wiki/images/5/53/Freecad-windows-install-04.jpg)
7. That's it, FreeCAD is installed. You will find it in your start menu.
![FreeCAD installation on windows, step 5](http://www.freecadweb.org/wiki/images/0/0b/Freecad-windows-install-05.jpg)

**Installing a development version**

Packaging FreeCAD and creating installer takes some time and dedication, so usually, development (also called 
pre-release) versions are provided as .zip (or .7z) archives. These don't need to be installed, just unpack
them and lauch FreeCAD by double-clicking the FreeCAD.exe file that you will find inside. This also allows you to
keep both the stable and "unstable" versions together on the same computer.

### Installing on Linux

On most modern Linux distributions (Ubuntu, Fedora, OpenSUSE, Debian, Mint, Elementary, etc), FreeCAD can be installed
with the click of a button, directly from the software management application provided by your distribution (the
aspect of it can differ from the images below, each distribution uses its own tool:)

1. Open the software manager and search for "freecad":
![FreeCAD installation on linux, step 1](http://www.freecadweb.org/wiki/images/4/4e/Freecad-linux-install-01.jpg)
2. Click the "install" button and that's it, FreeCAD gets installed. Don't forget to rate it afterwards!
![FreeCAD installation on linux, step 2](http://www.freecadweb.org/wiki/images/6/6f/Freecad-linux-install-02.jpg)

**Alternative ways**

One of the big joys of using Linux is the multitude of possibilities to tailor your software, so don't refrain
yourself: On Ubuntu and derivatives, FreeCAD can also be installed from a 
[PPA](https://launchpad.net/~freecad-maintainers) maintained by the FreeCAD
community (it contains both stable and development versions), and, since this is open-source software, you
can also easily [compile FreeCAD yourself](http://www.freecadweb.org/wiki/index.php?title=Compiling).

### Installing on  Mac OS

### Uninstalling

Hopefully you won't want to do that, but it is good to know anyway. On Windows and Linux, uninstalling FreeCAD
is very straightforward. Use the standard "remove software" option found in the control panel on Windows, or remove it
with the same software manager you used to install FreeCAD on Linux.

### Setting basic preferences

Once FreeCAD is installed, you might want to open it and set a couple of preferences. Preferences settings in
FreeCAD are located under menu Edit -> Preferences. You can browse through the different pages to see if there is
anything else you would want to change, but here are a couple of basic ones:

1. **Language**: FreeCAD will automatically pick the language of your operating system, but you might want to change that. FreeCAD is almost fully translated to 5 or 6 languages, plus many others that are at the moment only partially translated. You can easily [help to translate FreeCAD](https://crowdin.com/project/freecad).
![freecad basic options, step 1](http://www.freecadweb.org/wiki/images/f/f1/Freecad-basic-options01.jpg)
2. **Auto-load module**: Normally, FreeCAD will start showing you the start center page. You can skip this and begin a FreeCAD session directly in the workbench of your choice.
3. **Create document at startup**: Combined with the option above, this starts FreeCAD ready for work.
![freecad basic options, step 2](http://www.freecadweb.org/wiki/images/8/8e/Freecad-basic-options02.jpg)
4. **Storage options**: As any complex application, FreeCAD might crash from time to time. Here you can configure a few options that will help you to recover your work in case of a crash.
5. **Authoring and license**: You can set the defautl settings that will be used for your new files. Consider making your files shareable right from the start, by using a friendly license like [Creative Commons](https://creativecommons.org/).
6. **Redirect python messages to output view**: These two options are always good to mark, as they will permit you to see what's wrong in the Report View, when one of the python scripts running in FreeCAD has a problem.
![freecad basic options, step 3](http://www.freecadweb.org/wiki/images/1/19/Freecad-basic-options03.jpg)
7. **Units**: Here you can set the default units system you wish to use.
![freecad basic options, step 4](http://www.freecadweb.org/wiki/images/c/c5/Freecad-basic-options04.jpg)

### Installing additional content

As the FreeCAD project and its community grows quickly, and also thansk to being easy to extend,
external contributions and side-projects made by community members and other enthusiasts begin to 
appear everywhere on the internet. There is an effort going on to gather all these interesting additions in
one place, on the [FreeCAD github page](https://github.com/FreeCAD). There, among other things, you will find:

1. A **Parts library**, which contains all kinds of useful models or pieces of models, created by FreeCAD users, that can be freely used in your projects. The library can be used and accessed right from inside your FreeCAD installation thanks to a macro.
2. A **collection of addons**, most of them additional workbenches, that extend the functionality of FreeCAD for certain tasks.

**Read more**

* More download options: http://www.freecadweb.org/wiki/index.php?title=Download
* Detailed installation instructions: http://www.freecadweb.org/wiki/index.php?title=Installing
* FreeCAD PPA for Ubuntu: https://launchpad.net/~freecad-maintainers
* Compile FreeCAD yourself: http://www.freecadweb.org/wiki/index.php?title=Compiling
* FreeCAD translations: https://crowdin.com/project/freecad
* FreeCAD github page: https://github.com/FreeCAD
