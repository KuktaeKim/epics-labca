# Basic Information

## labCA is an EPICS Channel-Access Interface for SCILAB and MATLAB

Further information, documentation and build/install instructions
can be found [here](https://till-s.github.io/epics-labca)

Quick instructions:

### RUN INSTRUCTIONS

 - point your `PATH` to bin/<arch>
 - point your `LD_LIBRARY_PATH` to `lib/<arch>` (linux/solaris only)
 - the environment variable 
   `PATH` (win32) / `LD_LIBRARY_PATH` (linux, solaris) may also
   have to point to your EPICS base `bin/<arch>` (win32) or
   `lib/<arch>` (linux, solaris)

#### MATLAB:
  - start matlab; 
  -   `addpath bin/<arch>/labca`
  - ready to go, type e.g. `help labca`
  >>> if MATLAB 2020b hangs, this is most likely
      due to MATLAB problems.
      Try setting `LD_PRELOAD` environment variable (prior to
      launching MATLAB):
        `setenv LD_PRELOAD <path_to_epics_base>/lib/<arch>/libCom.so`

#### SCILAB:
  - start scilab
  -   `exec bin/<arch>/labca.sce`
  - ready to go, type e.g. `help lca`

### BUILD FROM SOURCE

 - edit `configure/CONFIG` and set target application
   (`MAKEFOR=MATLAB`  or `MAKEFOR=SCILAB`)
   and (optionally) the installation directory.
   You can also enable (experimental) support
   for Ctrl-C handling there. With this feature
   enabled, you can interrupt lcaGet/lcaPut by
   hitting Ctrl-C on the keyboard.
   
 - edit `configure/RELEASE` to point to your
   installation directories of 
     * EPICS base
     * MATLAB
     * SCILAB

   and (WIN32 only)
     * set `MATLIB_SUBDIR` to point to your compiler
       dependent libmx/libmex versions.
 - set `EPICS_HOST_ARCH` environment
   variable.
 - run GNU make from this directory.
 - In order to build documentation you need more tools
   (pdflatex, latex2html and lynx). Building the documentation
   is skipped if any of these tools is missing.
    

T.S, 2006/4
