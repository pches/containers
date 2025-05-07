# Building R Containers with VM Host Singbuild

### Building R Containers with VM Host Singbuild

The following instructions demonstrate how to create customized containers for R. The general goal is to create a self-contained environment that contains all necessary files, libraries, and tools to run R and to build and install packages. By being a self-contained environment, users should be able to build their packages and not worry about mismatches between compiler and library versions, causing build errors.

The design of the container should have enough R packages installed to meet most users' needs without having to have extra packages added. Users can build packages into their own library space using the R\_LIBS environment variable and the proper "lib=" setting in their install.packages command.

<p class="callout warning">This document is not a tutorial on how to create Singularity definition files. It assumes here that the end-user is already familiar with how to craft a definition file. These instructions are specific to using the RISE container build host, singbuild.vmhost.psu.edu.</p>

To use singbuild, you must have an account along with sudo privileges on the system. Contave Chad Bahrmann or Jeff Nucciarone for details.

> Access to the host is via ssh.:  
>   
> ssh -p 1855 singbuild.vmhost.psu.edu

<p class="callout warning">On-campus access should not require you to be connected to the Global Protect VPN, while off-campus access requires a VPN connection.</p>

Definition files are available in the appropriate section of the ICDS RISE GitHub repository (currently GitLab, [https://git.psu.edu/rise-sw-stack](https://git.psu.edu/rise-sw-stack). PCHES-specific definition files are available from the PCHES GitHub repository [https://github.com/pches/.](https://github.com/pches/)

Build the definition file into a SIF with the following:

**sudo singularity build SIF\_FILE DEFINITION\_FILE**

> sudo singularity build ubuntu\_24.04\_modified\_v2.sif ubuntu\_24.04\_modified\_v2.def

This can take a while.

After the SIF builds, create a sandbox with the following:

**sudo singularity build --sandbox SANDBOX\_DIRECTORY SIF\_File**

> sudo singularity build --sandbox /tmp/ubuntu24-2 ubuntu\_24.04\_modified\_v2.sif

Upon success, you will see a message about your SIF file being created.

<p class="callout info">You will see messages similar to:  
  
INFO: Starting build...  
INFO: Verifying bootstrap image ubuntu\_24.04\_modified\_v2.sif  
INFO: Extracting local image...  
INFO: Creating sandbox directory...  
INFO: Build complete: /tmp/ubuntu24-2  
</p>

For the next step, start a writable shell using the container, using the sandbox directory you just created:

**sudo singularity shell --writable SANDBOX\_DIRECTORY**

> sudo singularity shell --writable /tmp/ubuntu24-2/

<p class="callout info">You may see a warning message like this one. You can safely ignore it during testing, and it should not occur when the container is used during production.  
  
WARNING: Error changing the container working directory. Using '/root' instead: chdir /home/nucci/Singularity\_ubuntu\_22\_04\_2024\_02\_definition: no such file or directory  
</p>

At the shell prompt **"Apptainer&gt;"** you may now begin running commands in the shell.

As the container is writable, you can add libraries and packages to both the OS and to R. It is important to keep track of these additions, as you may want to include them in the definition file if the additions are to be made permanent.

This is useful for testing to see how to add additional R packages, as you can work out what the commands are and what additions may be necessary. This prevents build errors when building containers from the definition file, as this process allows you to debug. For example, trying to install R package "sf" may require additional packages that may require OS libdev packages not already installed in the container. By working it out here, you save from later frustrations when building the container from the definition file.

<p class="callout info">It is good practice to enter the commands as you might want them to appear in the definition file. This way, you only have to cut and paste. For example, use "apt-get install -y" instead of "apt-get install". For R, use "R -e 'install.packages("package\_name")'".</p>

The current containers were built with trial and error using this method with a writable container.

Some of the container definition files still contain references to Perl CPAN packages required to run WBM. As the R containers aren't meant to also run WBM, those libraries have been commented out. It may be difficult to use a newer version of Ubuntu and R to host a WBM container, as there is a dependency on rgdal. rgdal is no longer supported, and libgdal-perl is no longer available. As such, further development of containers specific to running WBM will likely be older version where these packages remain supported.

