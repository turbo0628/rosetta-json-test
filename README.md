# PyRosetta json utility test

There's a "json not defined" error when compiling PyRosetta on Ubuntu 16.04 with gcc version 5.4.0, clang version 6.0.0. This problem should blame the compiler for incapable to find the namespace for the json symbol implicitly.

Therefore, I extracted a minimal test code from the Rosetta source code. You can use this repo to test if your own compiler has the same problem.

## Usage
```
cd utility
g++ --std=c++11 -c json_utilities.cc -I .. -I . -DJSON_SKIP_UNSUPPORTED_COMPILER_CHECK
```
