---
tags:
  - Coding
  - Cheatsheet
---

# **GDB**

_**Author:** Teun Engels_

---

## What is GDB

GDB (GNU Debugger) is a debugger for the :fontawesome-brands-linux: Linux operating system.

The debugger is a program that allows you to debug your program while it executes.

GDB offers 4 things to help you debug:

-    Start your program, specifying anything that might affect its behavior.
-    Make your program stop on specified conditions.
-    Examine what has happened, when your program has crashed.
-    Change things in your program, so you can experiment with correcting the effects of a bug.


## How to install GDB

!!! commands "To install gdb you can use the following commands"

    ```
    sudo apt-get update
    sudo apt-get install gdb
    ```

    To check your gdb version you can run

    ```
    gdb --version
    ```

## How to use GDB

To start GDB, you need to run the following command:

```
gdb
```

However its more convenient to use the following command:

```
gdb <filename> 
```
Where `<filename>` is the name of the file you want to debug.


### GDB commands

#### break `<function>`

Set a breakpoint at `<function>` (in file).
shortcut : `b`

---


#### run

Start your program.
shortcut : `r`

---

#### bt 

Backtrace display the program stack.
shortcut : `bt`

---

#### print `<expression>`

Display the value of an `<expression>`.
shortcut : `p`

---

#### c

Continue running your program.
shortcut : `c`

---

#### next

Step to the next line of code.
shortcut : `n`

---

#### quit

Quit GDB.
shortcut : `q`

---





    





