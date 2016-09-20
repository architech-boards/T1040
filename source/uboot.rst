.. index:: E2V

.. _uboote2v:

Qormino u-boot
==============

Qormino is a new hybrid component that embeds a QorIQ T1040 processor and 1 GB of memory (DDR3L with ECC) on the same substrate.
As it contains the DDR bus, that makes the design of a new platform faster. Meanwhile, the DDR controller has to be configured with the Qormino properties, depending on the design and the memory modules as well. In this page you will download the patch file that will allow you to build an u-boot compatible with Qormino board.
In order to follow the next steps correctly you have to install the **Linux® SDK 1.7 for QorIQ® Processors of NXP**.

1. Download this `patch <_static/u-boot.tar.gz>`_

2. Unzip the files in **/home/<ENTER YOUR HOME NAME>/QorIQ-SDK-V1.7-20141218-yocto/meta-fsl-ppc/recipes-bsp/u-boot/**

::

  tar -zxvf u-boot.tar.gz -C /home/<ENTER YOUR HOME NAME>/QorIQ-SDK-V1.7-20141218-yocto/meta-fsl-ppc/recipes-bsp/u-boot/

3. Now you will have in **u-boot** folder these files:

::

 u-boot
 |
 |- u-boot-qoriq_2014.07.bb
 |- u-boot-qoriq_%.bbappend
 |- files
    |- 0001-Set-DDR-controller-properties-for-QT1040.patch
    |- 0002-boards.patch

4. Launch Yocto environment using the commands:

::

 cd ~/QorIQ-SDK-V1.7-20141218-yocto/build_t1040rdb-64b_release/
 source ./SOURCE_THIS

5. Now you are ready to build the new u-boot version:

::

 bitbake virtual/bootloader

6. You will find the bootloader in the following path **/home/<ENTER YOUR HOME NAME>/QorIQ-SDK-V1.7-20141218-yocto/build_t1040rdb-64b_release/tmp/deploy/images/t1040rdb-64b**

