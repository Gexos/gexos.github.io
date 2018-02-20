---
layout: post
title: Standalone PySide2 wheels
tags: [python, pyside]
---

The Qt Company has yet to release official, standalone and pip-installable PySide2 wheels. However, since they made it possible to build standalone wheels successfully, I'm now building such unofficial, standalone wheels here using free CI services (thanks [Travis](https://travis-ci.org/) and [AppVeyor](https://www.appveyor.com/)!):


- [fredrikaverpil/pyside2-windows](https://github.com/fredrikaverpil/pyside2-windows)
- [fredrikaverpil/pyside2-macos](https://github.com/fredrikaverpil/pyside2-macos)
- [fredrikaverpil/pyside2-linux](https://github.com/fredrikaverpil/pyside2-linux)

<!--more-->

### Download

You'll find the wheels under "releases" in each repository and you can pip-install the wheels like so:

```bash
pip install <URL to wheel>
```

Since Github doesn't have a storage limit to releases as of writing this, I would expect the URLs to work nicely for the forseeable future.


### Version string nomenclature

The Qt Company still doesn't maintain the version string of PySide2, so therefore I'm tagging releases based on the date when they were built.

You can check the git commit's CI build log to fetch the `git log` output or check the date of each [pyside-setup](http://code.qt.io/cgit/pyside/pyside-setup.git/) branch to figure out which commit was built for a particular release.

If you're wondering what version you're running, you may be able to query any of the following to receive some hints, which became available in PySide2 [sometime in late August 2017](https://codereview.qt-project.org/#/c/202199/):

```python
PySide2.__build_date__  # the date when the package was built in iso8601 format
PySide2.__build_commit_date__ # the date of the top-level commit used to build the package
PySide2.__build_commit_hash__  # the SHA1 hash of the top-level commit
PySide2.__build_commit_hash_described__  # the result of 'git describe commmit'
```

### macOS deployment target platforms

For macOS, wheel naming is a little misleading. They may say `macosx_10_6` which indicates they were built using Python which was built on macOS 10.6. However, Qt itself was built on newer macOS versions and therefore the wheel won't work on 10.6. Instead these are the actual deployment target platforms:

- PySide2-5.6: macOS 10.7
- PySide2-5.9: macOS 10.10
