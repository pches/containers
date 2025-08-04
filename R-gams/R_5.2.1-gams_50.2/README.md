# R-gams/R_5.2.1-gams_50.2
This repository directory contains singularity container definition file used for the creation of containers that have a self-contaned environment with both R and GAMS.

## Files

- README.md - This file
- R_5.2.1-gams_50.2-ubuntu_24.04.def - Definition file using Ubuntu 24.04, R 5.2.1, and GAMS 50.2. No WBM support. 

## Notes

This repo contains only the definition file that is ued to create the container. No code is 
provided for GAMS, as the compressed tar file would exceed limits for file storage imposed by github.

Code may be downloaded from the vendor site: https://gams.com/download/

The tarball may also be available from various source within PSU ICDS, contact via icds@psu.edu for details.

***IMPORTANT NOTICE ***

GAMS IS LICENSED CODE! To build hte container, a GAMS license file, gamslice.txt, must be included. As GAMS is licensed software, license restrictions prevent us from including the license here. If this container is for authorized PCHES use, contact ICDS for the licnese file at icds@psu.edu. Be sure to mention this is for the PCHES project. You will be asked for verification.

The GAMS tarball and license file are to be placed in the appropriate location as listed in the definition file "Files" section.

NOTE:
 
As building containers requires host root access, containers for Roar must be built on a VM host dedicated to building singularity containers, singbuild.vmhost.psu.edu.

Notes for these builds are available via the ICDS Bookstack document, "Building R Containers with VM Host Singbuild" available via the ICDS internal website 
https://bookstack.hpc.psu.edu/books/jeffnucciarone/page/building-r-containers-with-vm-host-singbuild. 

A markdown formated version of that document is available in this repo, Building_Containers.md.

