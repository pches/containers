# containers
This repository contains singularity container definition files used for the creation of various containers used for various PCHES projects.

## Files

- LICENSE  - MIT License file 
- README.md - This file
- Building_Containers.md - markdown formatted document on how to build the containers for Roar/RC using these definition files.
- WBM/WBM_v24/Singularity_ubuntu_22_04_2024_02_definition.tgz  - compressed tar file containing patch files and definition file for Ubuntu 22.04 and support for WBM v24.x. There is no R built into this container.
- WDRG/ubuntu_22.04_wdrg.def - Definition file using Ubuntu 22.04 and required R (4.2.1) and GAMS (33.2.0 r4f23b21) versions for the WDRG project.
- R/R_4.1.2/ubuntu_22.04-r_4.1.2.def - Definition file using Ubuntu 22.04, R 4.1.2 and has perl support to run WBM v24.x.
- R/R_4.5.1/R_4.5.1_ubuntu_24.04.def—Definition file using Ubuntu 22.04 with R 4.5.1. This Ubuntu release does not support running WBM as the gdal library for Perl is not available.
- R-gams/R_4.5.1-gams_50.2/R_4.5.1-gams_50.2-ubuntu_24.04.def - Definition file using Ubuntu 24.04, R 4.5.1, and GAMS 50.2. No WBM support. See the README file in ./R-gams/R_5.2.1-gams_50.2/ for important information on the GAMS source code and license file.

## Notes

As building containers requires host root access, containers for Roar must be built on a VM host dedicated to building singularity containers, singbuild.vmhost.psu.edu.

Notes for these builds are available via the ICDS Bookstack document, "Building R Containers with VM Host Singbuild" available via the ICDS internal website 
https://bookstack.hpc.psu.edu/books/jeffnucciarone/page/building-r-containers-with-vm-host-singbuild. 
A markdown formated version of that document is available in this repo, Building_Containers.md.
