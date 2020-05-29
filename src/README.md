Example of using imgui with SFML from https://github.com/eliasdaler/imgui-sfml

I had to also install:
* libstdc++ (libvstdc++6-devel-gcc10)
* ( https://pypi.org/project/conan/ )
* libtool ( which brought dependencies: m4, automake, autoconf)
* python-xml ( for the error Failed to load the xcbgen Python package! )
    * maybe these also: python3-xcb-proto-devel and xcb-proto-devel
* Mesa-libGL-devel (for Could NOT find OpenGL (missing: OPENGL_opengl_LIBRARY OPENGL_glx_LIBRARY
                          OPENGL_INCLUDE_DIR))
* libudev-devel - Development files for libudev


In my linux GCC is the default compiler and conan expecting clang fails with:
```
CMake Error at conanbuildinfo.cmake:415 (message):
  Incorrect 'clang', is not the one detected by CMake: 'GNU'
```
Fix: `CC=/usr/bin/clang` in the cmake environment in CLION.

