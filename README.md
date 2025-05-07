# containers
This repository contains singularity container definition files used for the creation of various containers used for various PCHES projects.

## Files

- LICENSE  - MIT License file 
- README.md - This file
- Singularity_ubuntu_22_04_2024_02_definition.tgz  - compressed tar file containing patch files and definition file for Ubuntu 22.04 and support for WBM v24.x. There is no R built into this container.
- ubuntu_22.04-r_4.1.2.def - Definition file using Ubuntu 22.04, R 4.1.2 and has perl support to run WBM v24.x.
- ubuntu_24.04-r_4.5.0.def—Definition file using Ubuntu 22.04 with R 4.5.0. This Ubuntu release does not support running WBM as the gdal library for Perl is not available.

## Notes

As building containers requires host root access, containers for Roar must be built on a VM host dedicated to building singularity containers, singbuild.vmhost.psu.edu.

Notes for these builds are available via the ICDS Bookstack document, "Building R Containers with VM Host Singbuild" available via the ICDS internal website 
https://bookstack.hpc.psu.edu/books/jeffnucciarone/page/building-r-containers-with-vm-host-singbuild. 
