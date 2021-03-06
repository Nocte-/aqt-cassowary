Aqt.Cassowary
=============

[![Build Status]
  (https://travis-ci.org/AbletonAG/aqt-cassowary.svg?branch=master)]
(https://travis-ci.org/AbletonAG/aqt-cassowary)

Aqt.Cassowary (pronounced like *Acute Cassowary*) is a Qt plugin that
allows you to run a incremental linear constraint solver in QML
applications, providing a declarative interface that fits naturally in
the QML programming model.

It is a wrapper around [Rhea](https://github.com/Nocte-/rhea), which
is modern C++ implementation based on the original [Cassowary linear
constraint solver](http://constraints.cs.washington.edu/cassowary/).

### Incremental linear constraint what the heck...?

A linear constraint solver allows you to specify the relationship
between variables (constraints) without necessarily giving them
specific values.  The system can then automatically find values for
these variables that satisfy all the specified relationships. It is
incremental, because the constraints can change and the system reuses
previous solutions to provide stable results fast.

Cassowary is most useful for writing layout code for responsive
applications with very dynamic content.  It is the tool you need when
`anchors` or `QtQuick.Layouts` are too rigid for you.  Check the
examples in `examples` for more details.

Status
------

The library is currently under heavy active development.  The API is
not stable yet.  Use at your own risk.

Requirements
------------

Dependencies:
  - Qt (>= 5.3)
  - Boost (>= 1.54)
  - CMake (>= 2.8.12)

Test dependencies:
  - GoogleTest (https://chromium.googlesource.com/external/googletest.git)

Mac:
  - Xcode v5.1 or higher

Windows:
  - Visual Studio 2013

## Build and Test

```
  mkdir build
  cd build
  cmake ..
  cmake --build .
```

The unit tests can be executed with ctest:

```
  ctest -V
```

You might set the following variables:

- Boost_INCLUDE_DIR   to the folder, where Boost headers are found

In case the CMake files shipped with Qt are not found, set the CMAKE_PREFIX_PATH
to the Qt installation prefix. See the
[Qt5 CMake manual](http://qt-project.org/doc/qt-5/cmake-manual.html) for more.

Example:

```
  cmake .. -DCMAKE_PREFIX_PATH=~/Qt/Qt5.3.1/clang_64 \
  -DBoost_INCLUDE_DIR=/opt/local/include/
```

License
-------

Aqt.Casssowary is distributed under the MIT license (see LICENSE).

> Copyright (c) 2014, 2015 Ableton AG, Berlin
>
> Permission is hereby granted, free of charge, to any person obtaining a copy
> of this software and associated documentation files (the "Software"), to deal
> in the Software without restriction, including without limitation the rights
> to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
> copies of the Software, and to permit persons to whom the Software is
> furnished to do so, subject to the following conditions:
>
> The above copyright notice and this permission notice shall be included in
> all copies or substantial portions of the Software.
>
> THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
> IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
> FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
> AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
> LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
> OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
> THE SOFTWARE.
