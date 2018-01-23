# pyside2-windows

[![Build status](https://ci.appveyor.com/api/projects/status/fhgrc83ql9w09kei/branch/master?svg=true)](https://ci.appveyor.com/project/fredrikaverpil/pyside2-windows/branch/master) [![Latest release](http://github-release-version.herokuapp.com/github/fredrikaverpil/pyside2-windows/release.svg?style=flat)](https://github.com/fredrikaverpil/pyside2-windows/releases/latest)


<br><br>

## Sister projects

- [pyside2-linux](https://github.com/fredrikaverpil/pyside2-linux)
- [pyside2-macos](https://github.com/fredrikaverpil/pyside2-macos)
- pyside2-windows (this project)


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


## How does this work?


### AppVeyor setup

AppVeyor runs virtual Windows machines which are equipped with [preinstalled software](https://www.appveyor.com/docs/build-environment/#pre-installed-software), in which e.g. Python and Qt are already installed and available. Using a [build matrix](https://www.appveyor.com/docs/build-configuration/#build-matrix), multiple configurations can be defined and run the same commands as stipulated in the [`appveyor.yml`](appveyor.yml) file. Because of this, PySide2 builds are limited to whatever versions of e.g. Python and Qt are available at AppVeyor (which to date hasn't caused any problems).

The built PySide2 wheels are registered as artifacts and are attached to each AppVeyor build (see the "Artifacts" tab under each job's build. This also includes builds initiated by pull requests.

If a `git tag` initiated the AppVeyor job, a Github release is also peformed. All built wheels are deployed and attached to the Github release.

[Rolling builds](https://www.appveyor.com/docs/build-configuration/#rolling-builds) are enabled for this project in AppVeyor, which means that queued up jobs are cancelled if a new job is initiated.

<br><br>

### Tagging creates a new relese

Manual tagging causes AppVeyor to generate a Github release and attach the built wheels to it. Tag using semver (`[v]major.minor.patch` or `YY.MM.DD`), e.g. `2018.01.01`, since PySide2 does not yet have a maintained version string.

```bash
git commit -am "Commit all changes..."
git push  # triggers an AppVeyor build
git tag 2018.01.01
git push origin 2018.01.01  # cancels previous build, starts new build and generates release
```
