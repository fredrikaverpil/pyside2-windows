# pyside2-windows

[![Build status](https://ci.appveyor.com/api/projects/status/fhgrc83ql9w09kei/branch/master?svg=true)](https://ci.appveyor.com/project/fredrikaverpil/pyside2-windows/branch/master)

This is a (possibly temporary?) development/research repository for building standalone PySide2 wheels on Windows.


### Download the standalone wheels

1. Enter the [AppVeyor build history](https://ci.appveyor.com/project/fredrikaverpil/pyside2-windows/history)
1. Click one of the green builds
1. Click one of the jobs (depending on which version you want)
1. Click on the "ARTIFACTS" link
1. Download the wheel



### To do

- [x] Build PySide2 standalone wheels (5.6, 5.9 branches) for Windows
- [x] Add built wheels as artifacts to the AppVeyor builds
- [ ] Attach built wheels to tagged releases?


### Known issues

**Build**
- libxml2/libxslt libraries are not installed/available

**Upstream issues**
- [PYSIDE-356](https://bugreports.qt.io/browse/PYSIDE-356) pyside2uic of pyside-tools installs for Python 3 only
- [PYSIDE-357](https://bugreports.qt.io/browse/PYSIDE-357) Compiler module missing from pyside2uic

