# yocto-wandboard-solo

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
   $: export MACHINE=wandboard-dual
   $: . ./setup-environment build
   $: bitbake core-image-minimal


#ERROR:
make: *** [all] Error 2
ERROR: oe_runmake failed


