Introduction
============
This package provides a Python API to inspect and validate [NeXus 
files](http://www.nexusformat.org/) written in the HDF5 format.  

The latest development version is always available from [NeXpy's GitHub
repository](https://github.com/nexpy/nxvalidate).

Please note that the code in this package has now been integrated into 
the [nexusformat package](https://github.com/nexpy/nexusformat) since 
v2.0.0. Developments on this package will be frozen.

Installation
============
Released versions of `nxvalidate` can be installed using

```
    % pip install nxvalidate
```

The source code can be downloaded from the NeXpy Git repository:

```
    % git clone http://github.com/nexpy/nxvalidate.git
```

Prerequisites
-------------
The only prerequisite required to install the `nxvalidate` package is
the [nexusformat package](https://github.com/nexpy/nexusformat). There
are more details of further dependencies in the [NeXpy
documentation](http://nexpy.github.io/nexpy).

Usage
=====
At the moment, the `nxvalidate` package provides a single command-line script.

```
% nxinspect -h
usage: nxinspect [-h] [-f FILENAME] [-p PATH] [-a [APPLICATION]]
                 [-b BASECLASS] [-i] [-w] [-e] [-v]

Inspects and validates NeXus files.

options:
  -h, --help            show this help message and exit
  -f FILENAME, --filename FILENAME
                        name of the NeXus file to be validated
  -p PATH, --path PATH  path to group to be validated in the NeXus file
  -b BASECLASS, --baseclass BASECLASS
                        name of the base class to be listed
  -a [APPLICATION], --application [APPLICATION]
                        validate the NeXus file against its application definition
  -d DEFINITIONS, --definitions DEFINITIONS
                        path to the directory containing NeXus definitions
  -i, --info            output info messages in addition to warnings and errors
  -w, --warning         output info messages in addition to warnings and errors
  -e, --error           output info messages in addition to warnings and errors
  -v, --version         show program's version number and exit
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
2. To compare the contents of a NeXus file with the base classes defined
   in a different directory to the installed package, type:
   ```
   % nxinspect -f <filename.nxs> -d /path/to/definitions
   ```
   The directory should contain two sub-directories, `applications` and
   `base_classes` containing the NXDL files needed to validate the
   specified NeXus file.
3. To check whether the contents of the NeXus file conform to the
   required contents of the application definition specified in the
   file, type:
   ```
   % nxinspect -f <filename.nxs> -a
   ```
4. To check whether the contents of the NeXus file conform to the
   required contents of an application definition file, type:
   ```
   % nxinspect -f <filename.nxs> -a <application.nxdl.xml>
   ```
5. To print the contents of a base class, type:
   ```
   % nxinspect -b <base-class-name>
   ```

User Support
============
Information about the Python API for reading and writing NeXus files is
available as part of the [NeXpy
documentation](https://nexpy.github.io/nexpy). If you have any general
questions concerning the use of this package, please address them to the
[NeXus Mailing
List](http:s//download.nexusformat.org/doc/html/mailinglist.html). If
you discover any bugs, please submit a [Github
issue](https://github.com/nexpy/nxvalidate/issues), preferably with
relevant tracebacks.

Acknowledgements
================
This package was developed jointly by Kaitlyn Marlor, Justin Wozniak,
and Ray Osborn. The NeXus data format standard has been developed under
the supervision of the [NeXus International Advisory
Committee](https://www.nexusformat.org/NIAC.html).
