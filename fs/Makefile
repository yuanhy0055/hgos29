#
# Makefile for the Linux filesystems.
#
# 14 Sep 2000, Christoph Hellwig <hch@infradead.org>
# Rewritten to use lists instead of if-statements.
# 

obj-y :=	open.o read_write.o file_table.o super.o \
		char_dev.o stat.o exec.o pipe.o namei.o fcntl.o \
		ioctl.o readdir.o select.o fifo.o dcache.o inode.o \
		attr.o bad_inode.o file.o filesystems.o namespace.o \
		seq_file.o xattr.o libfs.o fs-writeback.o \
		pnode.o drop_caches.o splice.o sync.o utimes.o \
		stack.o fs_struct.o

ifeq ($(CONFIG_BLOCK),y)
obj-y +=	buffer.o bio.o block_dev.o direct-io.o mpage.o ioprio.o
else
obj-y +=	no-block.o
endif

obj-$(CONFIG_BLK_DEV_INTEGRITY) += bio-integrity.o
obj-y				+= notify/
obj-$(CONFIG_EPOLL)		+= eventpoll.o
obj-$(CONFIG_ANON_INODES)	+= anon_inodes.o
obj-$(CONFIG_SIGNALFD)		+= signalfd.o
obj-$(CONFIG_TIMERFD)		+= timerfd.o
obj-$(CONFIG_EVENTFD)		+= eventfd.o
obj-$(CONFIG_AIO)               += aio.o
obj-$(CONFIG_FILE_LOCKING)      += locks.o
obj-$(CONFIG_COMPAT)		+= compat.o compat_ioctl.o

nfsd-$(CONFIG_NFSD)		:= nfsctl.o
obj-y				+= $(nfsd-y) $(nfsd-m)

obj-$(CONFIG_BINFMT_AOUT)	+= binfmt_aout.o
obj-$(CONFIG_BINFMT_EM86)	+= binfmt_em86.o
obj-$(CONFIG_BINFMT_MISC)	+= binfmt_misc.o

# binfmt_script is always there
obj-y				+= binfmt_script.o

obj-$(CONFIG_BINFMT_ELF)	+= binfmt_elf.o
obj-$(CONFIG_COMPAT_BINFMT_ELF)	+= compat_binfmt_elf.o
obj-$(CONFIG_BINFMT_ELF_FDPIC)	+= binfmt_elf_fdpic.o
obj-$(CONFIG_BINFMT_SOM)	+= binfmt_som.o
obj-$(CONFIG_BINFMT_FLAT)	+= binfmt_flat.o

obj-$(CONFIG_FS_MBCACHE)	+= mbcache.o
obj-$(CONFIG_FS_POSIX_ACL)	+= posix_acl.o xattr_acl.o
obj-$(CONFIG_NFS_COMMON)	+= nfs_common/
obj-$(CONFIG_GENERIC_ACL)	+= generic_acl.o

obj-$(CONFIG_PROC_FS)		+= proc/
obj-y				+= partitions/
obj-$(CONFIG_SYSFS)		+= sysfs/
obj-$(CONFIG_CONFIGFS_FS)	+= configfs/
obj-y				+= devpts/

obj-$(CONFIG_PROFILING)		+= dcookies.o
# Do not add any filesystems before this line
obj-$(CONFIG_EXT3_FS)		+= ext3/ # Before ext2 so root fs can be ext3
obj-$(CONFIG_EXT2_FS)		+= ext2/
# We place ext4 after ext2 so plain ext2 root fs's are mounted using ext2
# unless explicitly requested by rootfstype
obj-$(CONFIG_JBD)		+= jbd/
obj-$(CONFIG_JBD2)		+= jbd2/
obj-$(CONFIG_SQUASHFS)		+= squashfs/
obj-y				+= ramfs/
obj-$(CONFIG_HUGETLBFS)		+= hugetlbfs/
obj-$(CONFIG_FAT_FS)		+= fat/
obj-$(CONFIG_NFS_FS)		+= nfs/
obj-$(CONFIG_EXPORTFS)		+= exportfs/
obj-$(CONFIG_NFSD)		+= nfsd/
obj-$(CONFIG_LOCKD)		+= lockd/
obj-$(CONFIG_NLS)		+= nls/
obj-$(CONFIG_ROMFS_FS)		+= romfs/
obj-$(CONFIG_AUTOFS_FS)		+= autofs/
obj-$(CONFIG_AUTOFS4_FS)	+= autofs4/
obj-$(CONFIG_FUSE_FS)		+= fuse/
obj-$(CONFIG_DEBUG_FS)		+= debugfs/