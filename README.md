# pyside2-windows

[![Build status](https://ci.appveyor.com/api/projects/status/fhgrc83ql9w09kei/branch/master?svg=true)](https://ci.appveyor.com/project/fredrikaverpil/pyside2-windows/branch/master)

Unoffical PySide2 standalone wheels for Windows.

:fire: _Official_ wheels are [now available](http://blog.qt.io/blog/2018/06/13/qt-python-5-11-released/)!


## Sister projects

- [pyside2-linux](https://github.com/fredrikaverpil/pyside2-linux)
- [pyside2-macos](https://github.com/fredrikaverpil/pyside2-macos)
- pyside2-windows (this project)


## Download the standalone wheels

[Releases](https://github.com/fredrikaverpil/pyside2-windows/releases) contain built PySide2 wheels.

If you wish to check the wheels produced by e.g. a PR, see the [AppVeyor build history](https://ci.appveyor.com/project/fredrikaverpil/pyside2-windows/history), navigate to a build and download the attached artifacts. Note that the artifacts will be deleted after [some time](https://www.appveyor.com/docs/packaging-artifacts/#artifacts-retention-policy).


## How does this work?


### AppVeyor setup

AppVeyor runs virtual Windows machines which are equipped with [preinstalled software](https://www.appveyor.com/docs/build-environment/#pre-installed-software), in which e.g. Python and Qt are already installed and available. Using a [build matrix](https://www.appveyor.com/docs/build-configuration/#build-matrix), multiple configurations can be defined and run the same commands as stipulated in the [`appveyor.yml`](appveyor.yml) file. Because of this, PySide2 builds are limited to whatever versions of e.g. Python and Qt are available at AppVeyor (which to date hasn't caused any problems).

The built PySide2 wheels are registered as artifacts and are attached to each AppVeyor build (see the "Artifacts" tab under each job's build. This also includes builds initiated by pull requests.

If a `git tag` initiated the AppVeyor job, a Github release is also peformed. All built wheels are deployed and attached to the Github release.

[Rolling builds](https://www.appveyor.com/docs/build-configuration/#rolling-builds) are enabled for this project in AppVeyor, which means that queued up jobs are cancelled if a new job is initiated.


### A note on Upstream issues

All upstream issues should be reported in the [official PySide issue tracker](https://bugreports.qt.io/projects/PYSIDE/issues).

Note: PRs attempting to fix upstream fixes will not be accepted. Please send your PR upstream instead.


### Ask questions in the PySide/PySide2 gitter

If you have any general questions, please check out the [PySide2 Gitter community](https://gitter.im/PySide/pyside2). If you prefer IRC, check out `#qt-pyside` on irc.freenode.net.


### Useful links

- [PySide2 website](https://wiki.qt.io/PySide2)
- [Coin CI pyside-setup](https://testresults.qt.io/coin/?project=pyside%2Fpyside-setup)
- Supported platforms and configurations
  - [Qt 5.6](https://doc.qt.io/qt-5.6/supported-platforms-and-configurations.html)
  - [Qt 5.9](https://doc.qt.io/qt-5.9/supported-platforms-and-configurations.html)
  - [Qt 5.10](https://doc.qt.io/qt-5.10/supported-platforms-and-configurations.html)
