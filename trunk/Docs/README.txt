Amithlon Revival Project
========================

You will require the Amiga ROM and ramdisk images from an Amithlon CD, and an isolinux setup
to boot any modified Amithlon kernel builds at present.

A method to produce your own ramdisk images etc with your own Amiga ROM images and Workbench
files will be created in due course.

Directories
===========

Docs/Amithlon-new_kernel-2.4.19-pre4/
-------------------------------------

This directory contains a rough diff
of the original Linux 2.4.19-pre4 tree
and the updated kernel sources from 
amithlon.net.

I suspect that despite the version data in 
include/linux/version.h being consistant
that the updated kernel was based on a
release/SVN state other than pure 2.4.19-pre4
as there is some non-Amithlon differences
between the two.

As well as the .diff - files added to the
kernel tree in Amithlon are also present in
this tree.



Booting Amithlon
================

isolinux
--------

The following will give you 2 isolinux menu entries for booting smallird and bigird ramdisk images
from an iso9660 image/disc, remember to replace the kernel and ramdisk paths:

LABEL Amithlon_Small
MENU LABEL Amithlon - Small  
KERNEL /Boot/kernel
APPEND init=/linuxrc console_level=9 root=/dev/ram0 initrd=/Boot/smallird.gz vga=769 ramdisk_size=2310 leavepages=5200

LABEL Amithlon_Big
MENU LABEL Amithlon - Big 
KERNEL /Boot/kernel
APPEND init=/linuxrc console_level=9 root=/dev/ram0 initrd=/Boot/bigird.gz vga=769 ramdisk_size=12010 leavepages=7400



