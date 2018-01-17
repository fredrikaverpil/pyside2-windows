# pyside2-windows

[![Build status](https://ci.appveyor.com/api/projects/status/fhgrc83ql9w09kei/branch/master?svg=true)](https://ci.appveyor.com/project/fredrikaverpil/pyside2-windows/branch/master) [![Latest release](http://github-release-version.herokuapp.com/github/fredrikaverpil/pyside2-windows/release.svg?style=flat)](https://github.com/fredrikaverpil/pyside2-windows/releases/latest)

:warning: This is a (possibly temporary?) development/research repository for building standalone PySide2 wheels on Windows.

<br><br>


## Download the standalone wheels

[Releases](https://github.com/fredrikaverpil/pyside2-windows/releases) contain built PySide2 wheels.

If you wish to check the wheels produced by e.g. a PR, see the [AppVeyor build history](https://ci.appveyor.com/project/fredrikaverpil/pyside2-windows/history), navigate to a build and download the attached artifacts.

<br><br>


## Known issues

### Build issues

- `libxml2`/`libxslt` libraries are not installed/available. Is is also my understanding that the Windows version of PySide2 does not yet support these anyways.

### Upstream issues

All upstream issues should be reported in the [official PySide issue tracker](https://bugreports.qt.io/projects/PYSIDE/issues).

Note: PRs attempting to fix upstream fixes will not be accepted. Please send your PR upstream instead.

<br><br>


## Notes tagging for a release

Manual tagging causes Travis CI to generate a Github release and attach the built wheels to it. Tag using semver (`major.minor.patch`) but using the date of tagging/building, e.g. `2018.01.01`, since PySide2 does not yet have a maintained version string.

```bash
git commit -am "Commit all changes..."
git push  # triggers an AppVeyor build
git tag 2018.01.01
git push origin 2018.01.01  # cancels previous build, starts new build and generates release
```
