# TinyCrypt Cryptographic Library
Copyright (c) 2017, Intel Corporation. All rights reserved.  
  
![Workflow Badge](https://github.com/Receiver1/tinycrypt/actions/workflows/cmake-single-platform.yml/badge.svg)

## Overview:

The TinyCrypt Library provides an implementation for constrained devices of a 
minimal set of standard cryptography primitives. 

Please, ***SEE THE WIKI PAGE*** for more information on the supported 
cryptographic primitives and the limitations of TinyCrypt library. For usage,
security and technicalities, please see the corresponding header file of each 
cryptographic primitive. 

## Organization:

* /lib: C source code of the cryptographic primitives.
  - include/tinycrypt: C header files of the cryptographic primitives.
* /tests: Test vectors of the cryptographic primitives.

## Building:

1) In CMakeLists.txt set: 
    - ENABLE_TESTS for enabling (true) or disabling (false) tests compilation.
2) mkdir build & cd build
3) cmake ..
4) cmake --build . --config Release
5) ctest -C Release
