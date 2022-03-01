# Installation (Manual)
You will need the following packages to run bCNC
- tkinter the graphical toolkit for python
  Depending your python/OS it can either be already installed,
  or under the names tkinter, python3-tkinter, python-tk
- pyserial or under the name python-serial, python-pyserial
- numpy
- Optionally:
- python-imaging-tk: the PIL libraries for autolevel height map
- python-opencv: for webcam streaming on web pendant
- scipy: for 100 times faster 3D mesh slicing

Expand the directory or download it from github
and run the bCNC command

# Installation (Linux package maintainers)
- Copy `bCNC` subdirectory of this repo to `/usr/lib/python3.x/site-packages/`
- Launch using `python -m bCNC` or install bCNC.sh to /usr/bin
- Alternatively you can fetch the bCNC Python package using pip when building Linux package
  - refer to your distro, eg.: https://wiki.archlinux.org/index.php/Python_package_guidelines
  - Py2deb to build Debian package from Python package: https://pypi.org/project/py2deb/

# Installation (Compile to Windows .exe)

Note that you might probably find some precompiled .exe files on github "releases" page:
https://github.com/vlachoudis/bCNC/releases
But they might not be up to date.

This is basic example of how to compile bCNC to .exe file.
(given that you have working bCNC in the first place, eg. using `pip install bCNC`).
Go to the directory where is your bCNC installed and do the following:

    pip install pyinstaller
    pyinstaller --onefile --distpath . --hidden-import tkinter --paths lib;plugins;controllers --icon bCNC.ico --name bCNC __main__.py

This will take a minute or two. But in the end it should create `bCNC.exe`.
Also note that there is `make-exe.bat` file which will do just that for you.
This will also create rather large "build" subdirectory.
That is solely for caching purposes and you should delete it before redistributing!

If you are going to report bugs in .exe version of bCNC,
please check first if that bug occurs even when running directly in python (without .exe build).
