ARL OpenSHMEM for Epiphany
======

OpenSHMEM is a standardized interface to enable portable applications for
partitioned global address space (PGAS) architectures. This repository includes
the *ARL OpenSHMEM for Epiphany* implementation for optimized one-sided
communication, atomic, and collective operations for the
[Adapteva](http://adapteva.com) Epiphany microarchitecture on the [Parallella
board](http://parallella.org) (see [./src](./src)). Also included are
microbenchmarks and test codes (see [./test](./test)). These codes require the
COPRTHR-2 SDK. The library may be used without COPRTHR-2 and has been tested
with the Parabuntu 2016.11 release.

The OpenSHMEM implementation is based on the [OpenSHMEM 1.3
Specification](http://openshmem.org/site/sites/default/site\_files/OpenSHMEM-1.3.pdf)

The software was developed at the US Army Research Laboratory, Computational
Sciences Division, Computing Architectures Branch.

Prerequisites
-----

All code has been tested on the [2015.1 Parallella
image](http://ftp.parallella.org/ubuntu/dists/trusty/image/).

In order to build the codes in [./test](./test), you need to download and
install the [COPRTHR-2 SDK](http://www.browndeertechnology.com/coprthr2.htm).
The library is free for non-commercial use.

-----

OpenSHMEM and SHMEM are trademarks of Silicon Graphics International Corp. See
the [official OpenSHMEM website](http://openshmem.org/) for additional
information.
