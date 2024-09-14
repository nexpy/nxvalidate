Introduction
============
This package provides a Python API to inspect and validate [NeXus 
files](http://www.nexusformat.org/) written in the HDF5 format.  

The latest development version is always available from [NeXpy's GitHub
repository](https://github.com/nexpy/nxvalidate).

Installation
============
Released versions of `nxvalidate` can be installed using either

```
    $ pip install nxvalidate
```

The source code can be downloaded from the NeXpy Git repository:

```
    $ git clone http://github.com/nexpy/nxvalidate.git
```

Usage
=====
At the moment, the `nxvalidate` package provides a single command-line script.

```
% nxinspect -h
usage: nxinspect [-h] [-f FILENAME] [-p PATH] [-b BASECLASS] [-a] [-i] [-d] [-w] [-e]

Validates NeXus files.

options:
  -h, --help            show this help message and exit
  -f FILENAME, --filename FILENAME
                        name of the NeXus file to be validated
  -p PATH, --path PATH  path to group to be validated in the NeXus file
  -b BASECLASS, --baseclass BASECLASS
                        name of the base class to be listed
  -a, --application     validate the NeXus file against its application definition
  -i, --info            output info messages in addition to warnings and errors
  -d, --debug           output info messages in addition to warnings and errors
  -w, --warning         output info messages in addition to warnings and errors
  -e, --error           output info messages in addition to warnings and errors
```

> *N.B.*, the command is `nxinspect`, rather than `nxvalidate` to avoid
> confusion with the [C-library](https://github.com/nexusformat/cnxvalidate).

Examples
--------
1. To compare the contents of a NeXus file with the base classes defined
   by the NeXus standard and print conflicting fields or groups, type:
   ```
   % nxinspect -f <filename.nxs> -e
   ```
   The `--info`, `--warning` and `--error` switches control how much 
   information is output. The default is `--warning`.
2. To check whether the contents of the NeXus file conform to the
   required contents of its application definition, type:
   ```
   % nxinspect -f <filename.nxs> -a
   ```
3. To print the contents of a base class, type:
   ```
   % nxinspect -b <base-class-name>
   ```

Prerequisites
=============
The only prerequisite required to install the nxvalidate package is the 
[nexusformat package](https://github.com/nexpy/nexusformat). There are 
more details of further dependencies in the 
[NeXpy documentation](http://nexpy.github.io/nexpy).

* nexusformat          https://nexpy.github.io/nexpy

User Support
============
Consult the [NeXpy documentation](https://nexpy.github.io/nexpy) for details 
of both the Python command-line API and how to use the NeXpy GUI. If you have 
any general questions concerning the use of NeXpy, please address 
them to the 
[NeXus Mailing List](http:s//download.nexusformat.org/doc/html/mailinglist.html). 
If you discover any bugs, please submit a 
[Github issue](https://github.com/nexpy/nxvalidate/issues), preferably with 
relevant tracebacks.
