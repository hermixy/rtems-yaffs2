# Makefile for YAFFS direct stress tests
#
#
# YAFFS: Yet another Flash File System. A NAND-flash specific file system.
#
# Copyright (C) 2003-2010 Aleph One Ltd.
#
#
# Created by Charles Manning <charles@aleph1.co.uk>
#
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License version 2 as
# published by the Free Software Foundation.
#
# NB Warning this Makefile does not include header dependencies.
#
# $Id: Makefile,v 1.7 2010-02-25 22:34:47 charles Exp $

#EXTRA_COMPILE_FLAGS = -DYAFFS_IGNORE_TAGS_ECC

CFLAGS =      -DCONFIG_YAFFS_DIRECT -DCONFIG_YAFFS_YAFFS2  
CFLAGS +=     -DCONFIG_YAFFS_PROVIDE_DEFS -DCONFIG_YAFFSFS_PROVIDE_VALUES
CFLAGS +=    -Wall -g $(EXTRA_COMPILE_FLAGS) -Wstrict-aliasing 
#CFLAGS +=    -fno-strict-aliasing
CFLAGS +=    -O0
CFLAGS +=    -Wextra -Wpointer-arith
#CFLAGS +=    -DCONFIG_YAFFS_VALGRIND_TEST

#CFLAGS+=   -Wshadow -Wpointer-arith -Wwrite-strings -Wstrict-prototypes -Wmissing-declarations
#CFLAGS+=   -Wmissing-prototypes -Wredundant-decls -Wnested-externs -Winline


COMMONTESTOBJS = yaffscfg2k.o yaffs_ecc.o yaffs_fileem.o yaffs_fileem2k.o yaffsfs.o yaffs_guts.o \
		 yaffs_packedtags1.o yaffs_ramdisk.o yaffs_ramem2k.o \
		 yaffs_tagscompat.o yaffs_packedtags2.o yaffs_tagsvalidity.o yaffs_nand.o \
		 yaffs_checkptrw.o  yaffs_qsort.o\
		 yaffs_nameval.o yaffs_attribs.o \
		 yaffs_norif1.o  ynorsim.o  \
		 yaffs_allocator.o \
		 yaffs_bitmap.o \
		 yaffs_yaffs1.o \
		 yaffs_yaffs2.o \
		 yaffs_verify.o

#		 yaffs_checkptrwtest.o\

TESTFILES = 	quick_tests.o lib.o \
		test_yaffs_mount.o test_yaffs_mount_ENODEV.o test_yaffs_mount_ENAMETOOLONG.o test_yaffs_mount_EBUSY.o \
		test_yaffs_unmount.o test_yaffs_unmount_ENODEV.o test_yaffs_unmount_ENAMETOOLONG.o test_yaffs_unmount_EBUSY.o \
		test_yaffs_open.o test_yaffs_open_ENOENT.o test_yaffs_open_ENOTDIR.o test_yaffs_open_EEXIST.o test_yaffs_open_EISDIR.o test_yaffs_open_ENAMETOOLONG.o \
		test_yaffs_open_EINVAL.o test_yaffs_open_EINVAL2.o \
		test_yaffs_unlink.o  test_yaffs_unlink_EISDIR.o test_yaffs_unlink_ENOENT.o test_yaffs_unlink_ENAMETOOLONG.o test_yaffs_unlink_ENOTDIR.o\
		test_yaffs_ftruncate.o test_yaffs_ftruncate_EBADF.o test_yaffs_ftruncate_EINVAL.o test_yaffs_ftruncate_EFBIG.o \
		test_yaffs_truncate.o test_yaffs_truncate_ENOTDIR.o test_yaffs_truncate_EISDIR.o test_yaffs_truncate_ENOENT.o test_yaffs_truncate_EINVAL.o \
		test_yaffs_truncate_EFBIG.o\
		test_yaffs_write.o test_yaffs_write_EBADF.o test_yaffs_write_EFBIG.o \
		test_yaffs_read.o test_yaffs_read_EBADF.o test_yaffs_read_EINVAL.o\
		test_yaffs_lseek.o test_yaffs_lseek_EBADF.o test_yaffs_lseek_EINVAL.o test_yaffs_lseek_EFBIG.o \
		test_yaffs_access.o test_yaffs_access_EINVAL.o test_yaffs_access_ENOTDIR.o test_yaffs_access_ENOENT.o\
		test_yaffs_stat.o test_yaffs_stat_ENOENT.o test_yaffs_stat_ENOTDIR.o \
		test_yaffs_fstat.o test_yaffs_fstat_EBADF.o \
		test_yaffs_close_EBADF.o\
		test_yaffs_chmod.o test_yaffs_chmod_ENOENT.o test_yaffs_chmod_ENOTDIR.o test_yaffs_chmod_EINVAL.o \
		test_yaffs_fchmod.o test_yaffs_fchmod_EBADF.o\
		test_yaffs_fsync.o test_yaffs_fsync_EBADF.o \
		test_yaffs_fdatasync.o test_yaffs_fdatasync_EBADF.o \
		test_yaffs_mkdir.o test_yaffs_mkdir_EEXIST.o test_yaffs_mkdir_ENOTDIR.o \
		test_yaffs_fchmod.o test_yaffs_fchmod_EBADF.o test_yaffs_fchmod_EINVAL.o \
		test_yaffs_symlink.o test_yaffs_symlink_ENOTDIR.o

		  

YAFFSTESTOBJS  = $(COMMONTESTOBJS) $(TESTFILES)

PYTONOSYMLINKS = yaffs_error_converter.c yaffs_error_converter.h
PYTHONOBJS = yaffs_error_converter.o

ALLOBJS = $(sort $(YAFFSTESTOBJS)) $(PYTHONOBJS)

YAFFSSYMLINKS = yaffs_ecc.c yaffs_ecc.h yaffs_guts.c yaffs_guts.h yaffs_tagscompat.c yaffs_tagscompat.h \
          yaffs_packedtags1.c yaffs_packedtags1.h yaffs_packedtags2.c yaffs_packedtags2.h  yaffs_nandemul2k.h \
          yaffs_nand.c yaffs_nand.h yaffs_getblockinfo.h \
          yaffs_tagsvalidity.c yaffs_tagsvalidity.h yaffs_checkptrw.h yaffs_checkptrw.c \
          yaffs_nameval.c yaffs_nameval.h \
          yaffs_trace.h yaffs_attribs.h \
          yaffs_allocator.c yaffs_allocator.h \
          yaffs_yaffs1.c yaffs_yaffs1.h \
          yaffs_yaffs2.c yaffs_yaffs2.h \
          yaffs_bitmap.c yaffs_bitmap.h \
          yaffs_verify.c yaffs_verify.h

YAFFSDIRECTSYMLINKS =  yaffsfs.c yaffs_flashif.h yaffs_flashif2.h\
		       yaffsfs.h yaffs_malloc.h ydirectenv.h \
		       yaffs_flashif.c yaffscfg.h yaffs_qsort.c \
		       yaffs_nandemul2k.h yaffs_list.h \
		       yaffs_attribs.c \
		       yaffs_nandif.c yaffs_nandif.h yportenv.h


DIRECTEXTRASYMLINKS = 	yaffscfg2k.c yaffs_fileem2k.c yaffs_fileem2k.h\
			yaffs_fileem.c yaffs_norif1.c yaffs_norif1.h \
			yaffs_ramdisk.c yaffs_ramdisk.h yaffs_ramem2k.c \
			ynorsim.h ynorsim.c

SYMLINKS = $(YAFFSSYMLINKS) $(YAFFSDIRECTSYMLINKS) $(DIRECTEXTRASYMLINKS) $(PYTONOSYMLINKS)
#all: directtest2k boottest

all: quick_tests 

$(ALLOBJS): %.o: %.c
	gcc -c $(CFLAGS) -o $@ $<

$(PYTONOSYMLINKS):
	ln -s ../../python/$@ $@

$(YAFFSSYMLINKS):
	ln -s ../../../$@ $@

$(YAFFSDIRECTSYMLINKS):
	ln -s ../../$@ $@

$(DIRECTEXTRASYMLINKS):
	ln -s ../../basic-test/$@ $@


quick_tests: $(SYMLINKS) $(ALLOBJS)
	gcc $(CFLLAG) -o $@ $(ALLOBJS)






clean:
	rm -f quick_tests  $(ALLOBJS) core $(SYMLINKS) 