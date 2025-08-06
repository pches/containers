# WBM/WBM_v24
This repository contains singularity container definition files used for the creation of a container to support WBM v24.x.

## Files

- README.md - This file
- Singularity_ubuntu_22_04_2024_02_definition.tgz - The compressed tar file containing patch files and definition file for Ubuntu 22.04 and support for WBM v24.x. There is no R built into this container.

## Notes

This container build rgdal along with other required modules to run WBM

As building containers requires host root access, containers for Roar must be built on a VM host dedicated to building singularity containers, singbuild.vmhost.psu.edu.

Notes for these builds are available via the ICDS Bookstack document, "Building R Containers with VM Host Singbuild" available via the ICDS internal website 
https://bookstack.hpc.psu.edu/books/jeffnucciarone/page/building-r-containers-with-vm-host-singbuild. 
A markdown formated version of that document is available in this repo, Building_Containers.md.
