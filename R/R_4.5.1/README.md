# R/R_4.5.0
This repository directory contains the singularity container definition file used for the creation of containers that have a self-contained environment with R. 
R version: 4.5.1

## Files

- README.md - This file
- R_4.5.1-ubuntu_24.04.def - Definition file using Ubuntu 24.04, R 4.5.1. No WBM support. 

## Notes

This repo contains only the definition file used to create the container.

R Information:

The following packages and versions are built into the container:

      R -e 'install.packages("lhs", version="1.2.0", repos="https://cloud.r-project.org")'
      R -e 'install.packages("BASS", version="1.3.1", repos="https://cloud.r-project.org")'
      R -e 'install.packages("batchmeans", version="1.0.4", repos="https://cloud.r-project.org")'
      R -e 'install.packages("mcmcse", version="1.5.0", repos="https://cloud.r-project.org")'
      R -e 'install.packages("plot.matrix", version="1.6.2", repos="https://cloud.r-project.org")'
      R -e 'install.packages("RColorBrewer", version="1.1.3", repos="https://cloud.r-project.org")'
      R -e 'install.packages("ggplot2", version="3.5.2", repos="https://cloud.r-project.org")'
      R -e 'install.packages("gridExtra", version="2.3", repos="https://cloud.r-project.org")'
      R -e 'install.packages("dplyr", version="1.1.4", repos="https://cloud.r-project.org")'
      R -e 'install.packages("foreach", version="1.5.2", repos="https://cloud.r-project.org")'
      R -e 'install.packages("doParallel", version="1.0.17", repos="https://cloud.r-project.org")'
      R -e 'install.packages("snow", version="0.4.4", repos="https://cloud.r-project.org")'
      R -e 'install.packages("tidyverse", version="2.0.0", repos="https://cloud.r-project.org")'
      R -e 'install.packages("data.table", version="1.17.8", repos="https://cloud.r-project.org")'
      R -e 'install.packages("shiny", version="1.11.1", repos="https://cloud.r-project.org")'
      R -e 'install.packages("sensobol", version="1.1.5", repos="https://cloud.r-project.org")'
      R -e 'install.packages("GPfit", version="1.0.9", repos="https://cloud.r-project.org")'
      R -e 'install.packages("Rmpi", version="0.7.3.3", repos="https://cloud.r-project.org")'
      R -e 'install.packages("sf", version="1.0.21", repos="https://cloud.r-project.org")'
      R -e 'install.packages("terra", version="1.8.54", repos="https://cloud.r-project.org")'
      R -e 'install.packages("systemfonts", version="1.2.3", repos="https://cloud.r-project.org")'
      R -e 'install.packages("ggraph", version="2.2.1", repos="https://cloud.r-project.org")'
      R -e 'install.packages("ggridges", version="0.5.6", repos="https://cloud.r-project.org")'
      R -e 'install.packages("patchwork", version="1.3.1", repos="https://cloud.r-project.org")'
      R -e 'install.packages("tidyquant", version="1.0.11", repos="https://cloud.r-project.org")'
      R -e 'install.packages("caret", version="7.0.1", repos="https://cloud.r-project.org")'
      R -e 'install.packages("e1071", version="1.7.16", repos="https://cloud.r-project.org")'
      R -e 'install.packages("plotly", version="4.11.0", repos="https://cloud.r-project.org")'
      R -e 'install.packages("mlr3", version="1.0.1", repos="https://cloud.r-project.org")'
      R -e 'install.packages("xgboost", version="1.7.11.1", repos="https://cloud.r-project.org")'
      R -e 'install.packages("gamstransfer", version="3.0.6", repos="https://cloud.r-project.org")'
      R -e 'install.packages("R.utils", version="2.13.0", repos="https://cloud.r-project.org")'
      R -e 'install.packages("devtools", version="2.4.5", repos="https://cloud.r-project.org")'
      R -e 'install.packages("igraph", version="2.1.4", repos="https://cloud.r-project.org")'
      R -e 'install.packages("readr", version="2.1.5", repos="https://cloud.r-project.org")'
      R -e 'install.packages("assertthat", version="0.2.1", repos="https://cloud.r-project.org")'
      R -e 'install.packages("randtoolbox", version="2.0.5", repos="https://cloud.r-project.org")'
      R -e 'install.packages("raster", version="3.6.32", repos="https://cloud.r-project.org")'
      R -e 'install.packages("reshape2", version="1.4.4", repos="https://cloud.r-project.org")'

Build Information:
 
As building containers requires host root access, containers for Roar must be built on a VM host dedicated to building singularity containers, singbuild.vmhost.psu.edu.

Notes for these builds are available via the ICDS Bookstack document, "Building R Containers with VM Host Singbuild," available via the ICDS internal website 
https://bookstack.hpc.psu.edu/books/jeffnucciarone/page/building-r-containers-with-vm-host-singbuild. 

A markdown-formatted version of that document is available in this repo home directory, Building_Containers.md.

