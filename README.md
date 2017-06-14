
# step to bluid Wanboard Image:
 #1- Download and install Google's repo
  $: mkdir ~/bin
  $: curl http://commondatastorage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
  $: chmod a+x ~/bin/repo

 #2- create the BSP directory download all of the metedata for the BSP layers
   $: PATH=${PATH}:~/bin
   $: mkdir fsl-community-bsp
   $: cd fsl-community-bsp

 #3- Initialize the repositories
   $: repo init -u https://github.com/Freescale/fsl-community-bsp-platform -b dizzy
 
 #4- Download all of the metadata for the BSP layers
   $: repo sync
 
 #5- Setup environment and build an image
   $: export MACHINE=wandboard-solo
   $: . ./setup-environment build
   $: bitbake core-image-minimal


#ERROR:
make: *** [all] Error 2
ERROR: oe_runmake failed

The problem is here:
"*** Could not find autoconf 2.13. Stop."

Please install all build dependencies for Ubuntu as listed here:
https://developer.mozilla.org/en-US/docs/Developer_Guide/Build_Instructions/Linux_Prerequisites

#new ERROR
ERROR: oe_runconf failed


