---
layout: post
title: Compiling PySide2 from source
tags: [pyside, python]
---

![]({{ site.baseurl }}blog/assets/pyside2/pyside2_compile.png)

Here's how to compile PySide2 on Linux, Mac OS X and Windows.

[Maya 2017](http://www.autodesk.com/products/maya) shipped with [PySide2](https://wiki.qt.io/PySide2) built against [Qt](https://www.qt.io/developers/) 5.6.1, so that's the version of Qt I'm using in this guide as well as 64-bit [Python](https://www.python.org).

<!--more-->


## Prerequisites


### OS X

You'll need the Xcode commandline tools:

```
xcode-select --install
sudo xcodebuild -license
```

Then the following packages, easily installed via [brew](https://brew.sh):

```bash
brew install qt5 cmake libxslt libxml2
```

Please note, this installed Qt 5.6.1-1 and cmake 3.5.2 on my system.

### Ubuntu 14.04 Linux

Currently, I'm having issues with not being able to install `libqt5quickwidgets5` via `apt-get`, and because of that I recommend resorting to the following:

```bash
apt-get install python-pyside2  # for Python 2.7.x
apt-get install python3-pyside2  # for Python 3.5.x
```


### Ubuntu 16.04 Linux

I suggest you run a Docker container to build PySide2. This could be done by doing something like this:

```bash
# Map the current folder to the container's /pyside, so you can transfer built
# wheels onto your main machine
docker run -ti -v $(pwd):/pyside ubuntu:16.04 bash
```

You may want to start with an `apt-get update`, especially if you're in a Docker container.

Make sure you've got `pip` and the `wheel` package:

```bash
apt-get install python-pip  # or python3-pip (for Python 3.x)
```

Then you can get all needed dependencies with apt-get:

```bash
apt-get install build-essential git cmake qt5-default libxml2 libxslt1.1 python-dev qtbase5-dev
```

This installed Qt 5.5.1 and cmake 3.5.1 on my system. Please note that cmake version >=3.0 is required.

Additionally, you'll need to install Qt5's libraries:

```bash
apt-get install qttools5-dev-tools libqt5clucene5 libqt5concurrent5 libqt5core5a libqt5dbus5 libqt5designer5 libqt5designercomponents5 libqt5feedback5 libqt5gui5 libqt5help5 libqt5multimedia5 libqt5network5 libqt5opengl5 libqt5opengl5-dev libqt5organizer5 libqt5positioning5 libqt5printsupport5 libqt5qml5 libqt5quick5 libqt5quickwidgets5 libqt5script5 libqt5scripttools5 libqt5sql5 libqt5sql5-sqlite libqt5svg5 libqt5test5 libqt5webkit5 libqt5widgets5 libqt5xml5 libqt5xmlpatterns5 libqt5xmlpatterns5-dev
```

### Windows 10

Unfortunately, I have no idea how to compile PySide2 using Qt 5.6.1 for Python 2.7.x in Windows. I very much appreciate suggestions in the comments further down below on this. So, at least for now, this guide is for Python 3.5.x only.

You'll need OpenSSL, Cmake, Microsoft Visual C++ Studio 2015 and, of course, Qt5.

I think the nicest approach would be to install these softwares via [Chocolatey](https://chocolatey.org) but I haven't managed to get that to work flawlessly, so I'm doing this manually instead.

Download and install the 64-bit versions of:

* [OpenSSL](https://sourceforge.net/projects/openssl)
* [Cmake](https://cmake.org/download)
* [Microsoft Visual C++ Studio 2015](https://www.visualstudio.com) - Note: during the install, you must check the programming language option for C++, or the `cl` command won't be available. This can also be performed if you run the installer again after having already installed MSVS2015 (choose to "Modify" your installation).
* Qt 5.6.1-1 from the [Qt archives](https://download.qt.io/archive/qt/), I'm using [qt-opensource-windows-x86-msvc2015_64-5.6.1-1.exe](https://download.qt.io/archive/qt/5.6/5.6.1-1/qt-opensource-windows-x86-msvc2015_64-5.6.1-1.exe).

You might also need the Windows SDK (I'm not sure since I had it installed already when writing this). You can download it for Windows 10 from [here](https://developer.microsoft.com/en-us/windows/downloads/windows-10-sdk). I have a feeling this is installed by MSVS2015, but I'm not sure. If you know what the deal is here, please let me know in the comments further down below!


## Notes on prerequisites

PySide2 (or possibly Qt5?) requires Cmake >=3.0 to work. You can check your version with `cmake --version`.


## Clone the repository

The old repository is located in Github. I'm not sure why they still keep it there as it is no longer maintained. The active repositories is hosted by the Qt Company and resides [here](https://codereview.qt-project.org/#/admin/projects/?filter=pyside).

Clone the `pyside-setup` repository and have it also pull down its gitmodules:

```
git clone --recursive https://codereview.qt-project.org/pyside/pyside-setup
```

## Build the PySide2 wheel

The exact paths given in the arguments may not be identical on your system so verify those prior to compiling.

### OS X

This command worked fine for me using Python 2.7.11 and Python 3.5.1. Remember to have pip installed with the `wheel` package or you'll get an error about `bdist_wheel`.

```
python setup.py bdist_wheel --ignore-git --qmake=/usr/local/Cellar/qt5/5.6.1-1/bin/qmake --cmake=/usr/local/bin/cmake --openssl=/usr/local/Cellar/openssl/1.0.2h_1/bin
```

### Ubuntu 16.04 Linux


This command worked fine for me using Python 2.7.12 and Python 3.5.2. Remember to have pip installed with the `wheel` package or you'll get an error about `bdist_wheel`.

```
python setup.py bdist_wheel --ignore-git --qmake=/usr/lib/x86_64-linux-gnu/qt5/bin/qmake --cmake=/usr/bin/cmake
```

Please note, I'm not using the `--openssl` argument since I actually wasn't able to figure out where the OpenSSL bin directory resides in Ubuntu. At least, searching using `find / -name openssl` didn't reveal this and the wheel works anyways. If you know where this resides or how to make it available, I'd be grateful if you would like to share this with me in the comments further down below.


### Windows 10

Open the prompt called "VS2015 x64 Native Tools Command Prompt" and run the build command.

```
python setup.py bdist_wheel --ignore-git --qmake=c:\Qt\Qt5.6.1\5.6\msvc2015\bin\qmake.exe --openssl="C:\openssl-1.0.2d-fips-2.0.10\bin" --cmake="C:\Program Files\CMake\bin\cmake.exe"
```

## Install the wheel

A wheel was hopefully built in the `dist` folder. So just `cd dist` and `pip install` away!

## Closing comments

As of writing this, I understand that PySide2 is not seen as made generally available just yet, and could perhaps be seen as being in an alpha or beta stage. But they did announce that Python 2 support was officially dropped [here](https://github.com/PySide/pyside2/wiki):

> Why there is no PySide2 for Python 2? Because Python 2 extensions like PySide need to be compiled with ancient version of MS Visual C++ 9 and that means that all linked libs including Qt need to be compiled with this version. But Qt5, the library that PySide2 wraps, dropped support for MS VC++ 9, and code is unlikely to compile for it anymore. The only solution to fix this, is to help with development and funding of [https://mingwpy.github.io/](https://mingwpy.github.io/)

Since the Github repository is basically abandoned, I'd suggest you create a user account with The Qt Company and start checking out the repository over at Qt, where apparently the real action is:

* [PySide2 wiki](https://wiki.qt.io/PySide2)
* [PySide2 repositories](https://codereview.qt-project.org/#/admin/projects/?filter=pyside)
* [Bug tracker (issues)](https://bugreports.qt.io/browse/PYSIDE/)
* [Qt language bindings forum](htps://forum.qt.io/category/15/language-bindings)