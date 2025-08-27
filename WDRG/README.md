# WDRG

Container definition file for the WDRG project.
This container has the versions of R, R libraries, GDAL for the WBM version used for this project. The R / R library versions used are specified in the definition file. GAMS requires a specific version, see the notes below.

## Files

- README.md - This file
- ubuntu_22.04_wdrg.def - Singularity definition file for Ubuntu 22.04, R (v 4.2.1), and GAMS used for teh WDRG project.

## Notes

GAMS Information:

This repo contains only the definition file used to create the container. No code is 
provided for GAMS, as the compressed tar file would exceed the limits for file storage imposed by GitHub.

Code may be downloaded from the vendor site: https://gams.com/download/

The WDRG project requires GAMS version 33.2.0 r4f23b21.

The tarball may also be available from various sources within PSU ICDS; contact via icds@psu.edu for details.

*** IMPORTANT ***

*GAMS IS LICENSED CODE!* To build the container, a GAMS license file, gamslice.txt, must be included in the build directory. As GAMS is licensed software, license restrictions prevent us from including the license here. If this container is for authorized PCHES use, contact ICDS for the license file at icds@psu.edu. Be sure to mention this is for the PCHES project. You will be asked for verification.

You'll need to put the GAMS tarball and the license file into the folder specified in the **"Files"** section of the definition file.


This container build rgdal along with other required modules to run WBM

As building containers requires host root access, containers for Roar must be built on a VM host dedicated to building singularity containers, singbuild.vmhost.psu.edu.

Notes for these builds are available via the ICDS Bookstack document, "Building R Containers with VM Host Singbuild" available via the ICDS internal website 
https://bookstack.hpc.psu.edu/books/jeffnucciarone/page/building-r-containers-with-vm-host-singbuild. 
A markdown formated version of that document is available in this repo, Building_Containers.md.

