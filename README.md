# About

`functional_utils` (or just `futils`) is a general utils Python lib made  with an emphasis in a functional and procedural point of view. This means that we rarely use classes and methods and never use objects directly. When used, classes comes with static methods in order to define namespaces inside modules instead of to work as a blueprint for objects.
Furthermore, some Python methods are converted to plain functions.

We follow a constructivist and unifying approach, making use of parametric polymorphisms. We begin by redefining, generalizing and unifying the basic builtin Python operations/methods, which are then used in the construction of additional functions.

> **OBS.**
> * There are no dependences. Only builtin libs are used.
> * In Brazilian Portuguese, `futil` means `futile`. Interpret it as you wish :D

# Structure

The utils are divided into two categories:
1. `core`: primitive generic functions, to be called directly, without a namespace.
2. `mods`: context-based functions, consuming the core utils, to be called inside a namespace.

```
utils/
  |-- __init__.py ............. importing everything in core and each mod in a custom namespace
  |-- core/ ................... with the core utils
  |   |-- __init__.py ......... importing everything in every core utils 
  |   |-- asci.py ............. asci core module
  |   `...
  `-- mods/ ................... with the mods
      |-- re.py ............... regex-based module
      `-- ...
```

# Core

```
lib            description
---------------------------------------------
asci           definition of asci colors
logs           definition and configuration of logs
op             generalized basic operations
cmd            basic python commands and shell commands
date           functions related to date and time
hash           hashable types based functions
iter           iterable-based functions
var            tests related to variables
func           function-based operations
type           type/class-based operations
comp           generalized composite operations
```

# Mods
```
lib            description
----------------------------------------------
re             regex-based functions
path           functions related to the path type
json           operations for json data/files
http           http operations         
```

# Interdependence

The idea is to try to maintain a linear dependence among the utils, as below. To avoid cyclic imports we use local imports.

```
lib            imports          
----------------------------------------------
ansi           nothing
logs           ansi 
op             logs 
cmd            logs, op
date           logs, op
var            logs, op
hash           logs, op
func           logs, op
type           logs, op, func
comp           logs, op, var
iter           logs, op, str, var, comp
----------------------------------------------
lib            imports          
----------------------------------------------
re             core
path           core, re
json           core, re, path
http           core, json, path
```

# Usage

* With `git`: 
```bash
git clone https://github.com/ximenesyuri/futils /path/to/venv/lib/python3.x/site-packages/functional_utils
``` 
* With `pip`:
```bash
/path/to/venv/bin/pip3 install functional_utils
```
* With `poetry`:
```bash
poetry add functional_utils
```

> We suggest to import the lib as `from functional_utils import *`.

# Contributors

1. Yuri Ximenes: [github](https://github.com/ximenesyuri), [linkedin](https://linkedin.com/in/ximenesyuri)
2. Rafael David: [github](https://github.com/rdvid), [linkedin](https://www.linkedin.com/in/rdvid/)
