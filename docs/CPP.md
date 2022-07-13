---
tags:
  - Coding
  - C++
  - Cheatsheet
---

# C++ Guide

_**Author**: Teun Engels_

---

This is a basic guide for C++.

## What is C++

C++ is a [GPL](Definitions.md#gpl) developed by [Bjarne Stroustrup](https://en.wikipedia.org/wiki/Bjarne_Stroustrup)

C++ has lots of features

- [object-oriented programming](Definitions.md#object-oriented-programming)
- [generic programming](Definitions.md#generic-programming)
- [functional programming](Definitions.md#functional-programming)
- [low-level memory manipulation](Definitions.md#low-level-memory-manipulation)

## Setup

### Installing

First of all we need a way to program C++.

We have a few options but we will show the 2 most popular ones

- VS22

- Linux (Can also be VM or WSL)

#### VS22

The first option is Visual Studio (in this case Visual Studio Code 22).

- Here we need to go to Tools -> Get Tools & Features...

- Then a new menu will open

![VSMenu](img/VS22.png)

- Here we need to select `desktop development with C++`

- For the rest you just need to follow the installer

#### Linux

The second option is linux. 

!!! note

    g++ is the name of the C++ compiler

For this we need to use the terminal `Press Ctrl + Alt + T`

!!! commands
    
    To install g++ you need to run this command

    ```
    sudo apt-get update
    sudo apt-get install gcc
    sudo apt -get install g++
    sudo apt-get install build-essential
    ```

    To check your g++ version you can run

    ```
    g++ — version
    ```

    Later in this guide we will use a debugger [GDB]() but we can install it already

    ```
    sudo apt-get update
    sudo apt-get install gdb
    ```

    To check your GDB version you can run

    ```
    gdb --version
    ```



### File Types

#### .cpp

For C++ code we use a `.cpp` file so the [compiler]() knows we are using C++. 

`main.cpp` is the source code filename typically used for the main() function of a C++ program, where the program begins execution.

```cpp

#include <iostream>
using namespace std;

int main()
{
   cout<<std::endl<<"Hello World";
   // C++ returns 0 by default so there is no need to do it yourself (optional).
}

```

#### .h & .hpp

If you are at all familiar with C you probably know header files.

C++ is an extend of C so C++ also uses header files. These can either have a `.h` extention or `.hpp`.

A header file includes the following three things 

- Function definitions
- Data type definitions
- Macros

There are two types of header files

- **Pre-existing** header files: Files which are already available.
- **User-defined** header files: These files are defined by the user.

???+ code "Code Example"

    Here is an example of a basic header file implementation

    `main.cpp`

    ```cpp
    #include "sum.h"

    #include <iostream>
    using namespace std;

    int main()
    {
    SumOfTwo(3,4);
    }

    ```
    `sum.cpp`

    ```cpp
    #include "sum.h"

    int SumOfTwo(int a, int b)
    {
        return (a + b);
    }

    ```
    `sum.h`

    ```cpp
    #ifndef SUM_H
    #define SUM_H

    int SumOfTwo(int a, int b);

    #endif

    ```



### C++ Project Structure

Top-Level Directories:

```
build/ 
include/ 
src/ 
tests/ 
examples/ 
external/ 
data/ 
tools/ 
docs/ 
libs/ 
extras/ 
```

A lot of these Top-Level directories are not needed at the start so we shall ignore them for the beginning. But a few are important so we will take a futher look into them.

`build` is reserved for builds. So its special in that it must **not** be committed to a [Source Control System]().

`src` Source is very important here you will place your .cpp files. 

!!! note

    Header File Placement

    **Separate Placement**

    ```
    <>/
    include/
        utils/
            sorting.hpp
    src/
        utils/
            sorting.cpp
    ```

    **Combined Placement**

    ```
    <>/
    src/
        utils/
            sorting.cpp
            sorting.hpp
    ```

## Your first program




