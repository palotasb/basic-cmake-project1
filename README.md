# Basic CMake project with find_package support by using configure_package_config_file
Basic CMake project with find_package support by using configure_package_config_file

Usage:
```bash
$ mkdir -p build-a && mkdir -p build-b
$ cd build-a
$ cmake ../a && cmake --build .
$ cd ../build-b
$ cmake -DProjectA_DIR="`pwd`/../build-a" ../b && cmake --build .
```

Warning: installing Project A (with `make install` or `cmake --build <build-a-dir> --target install`) will not make all the dependencies available in the install location for use by Project B.
