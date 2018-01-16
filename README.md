# pyside2-windows

[![Build status](https://ci.appveyor.com/api/projects/status/fhgrc83ql9w09kei/branch/master?svg=true)](https://ci.appveyor.com/project/fredrikaverpil/pyside2-windows/branch/master)

This is a (possibly temporary?) development/research repository for building standalone PySide2 wheels on Windows.


### Download the standalone wheels

Tagged releases contain built PySide2 wheels.

If you wish to check the wheels produced by e.g. a PR, see the [AppVeyor build history](https://ci.appveyor.com/project/fredrikaverpil/pyside2-windows/history), navigate to a build and download the attached artifacts.


### Known issues

**Build**
- libxml2/libxslt libraries are not installed/available

**Upstream issues**
- [PYSIDE-356](https://bugreports.qt.io/browse/PYSIDE-356) pyside2uic of pyside-tools installs for Python 3 only
- [PYSIDE-357](https://bugreports.qt.io/browse/PYSIDE-357) Compiler module missing from pyside2uic

