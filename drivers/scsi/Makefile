#
# Makefile for linux/drivers/scsi
#
# 30 May 2000, Christoph Hellwig <hch@infradead.org>
# Rewritten to use lists instead of if-statements.
#
# 20 Sep 2000, Torben Mathiasen <tmm@image.dk>
# Changed link order to reflect new scsi initialization.
#
# *!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!
# The link order must be, SCSI Core, SCSI HBA drivers, and
# lastly SCSI peripheral drivers (disk/tape/cdrom/etc.) to
# satisfy certain initialization assumptions in the SCSI layer.
# *!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!*!


CFLAGS_aha152x.o =   -DAHA152X_STAT -DAUTOCONF
CFLAGS_gdth.o    = # -DDEBUG_GDTH=2 -D__SERIAL__ -D__COM2__ -DGDTH_STATISTICS

obj-$(CONFIG_SCSI)		+= scsi_mod.o
obj-$(CONFIG_SCSI_TGT)		+= scsi_tgt.o

obj-$(CONFIG_RAID_ATTRS)	+= raid_class.o

# --- NOTE ORDERING HERE ---
# For kernel non-modular link, transport attributes need to
# be initialised before drivers
# --------------------------
obj-$(CONFIG_SCSI_SPI_ATTRS)	+= scsi_transport_spi.o
obj-$(CONFIG_SCSI_FC_ATTRS) 	+= scsi_transport_fc.o
obj-$(CONFIG_SCSI_ISCSI_ATTRS)	+= scsi_transport_iscsi.o
obj-$(CONFIG_SCSI_SAS_ATTRS)	+= scsi_transport_sas.o
obj-$(CONFIG_SCSI_SRP_ATTRS)	+= scsi_transport_srp.o

obj-$(CONFIG_ISCSI_TCP) 	+= libiscsi.o	libiscsi_tcp.o iscsi_tcp.o
obj-$(CONFIG_INFINIBAND_ISER) 	+= libiscsi.o
obj-$(CONFIG_MAC_SCSI)		+= mac_scsi.o
obj-$(CONFIG_SCSI_MAC_ESP)	+= esp_scsi.o	mac_esp.o
obj-$(CONFIG_SUN3_SCSI)		+= sun3_scsi.o  sun3_scsi_vme.o
obj-$(CONFIG_MVME16x_SCSI)	+= 53c700.o	mvme16x_scsi.o
obj-$(CONFIG_BVME6000_SCSI)	+= 53c700.o	bvme6000_scsi.o
obj-$(CONFIG_SCSI_SIM710)	+= 53c700.o	sim710.o
obj-$(CONFIG_SCSI_ADVANSYS)	+= advansys.o
obj-$(CONFIG_SCSI_BUSLOGIC)	+= BusLogic.o
obj-$(CONFIG_SCSI_DPT_I2O)	+= dpt_i2o.o
obj-$(CONFIG_SCSI_U14_34F)	+= u14-34f.o
obj-$(CONFIG_SCSI_ULTRASTOR)	+= ultrastor.o
obj-$(CONFIG_SCSI_IPS)		+= ips.o
obj-$(CONFIG_SCSI_FD_MCS)	+= fd_mcs.o
obj-$(CONFIG_SCSI_PAS16)	+= pas16.o
obj-$(CONFIG_SCSI_T128)		+= t128.o
obj-$(CONFIG_SCSI_DTC3280)	+= dtc.o
obj-$(CONFIG_SCSI_ZALON)	+= zalon7xx.o
obj-$(CONFIG_SCSI_EATA_PIO)	+= eata_pio.o
obj-$(CONFIG_SCSI_IBMMCA)	+= ibmmca.o
obj-$(CONFIG_SCSI_EATA)		+= eata.o
obj-$(CONFIG_SCSI_DC395x)	+= dc395x.o
obj-$(CONFIG_SCSI_DC390T)	+= tmscsim.o
obj-$(CONFIG_MEGARAID_LEGACY)	+= megaraid.o
obj-$(CONFIG_SCSI_ACARD)	+= atp870u.o
obj-$(CONFIG_SCSI_SUNESP)	+= esp_scsi.o	sun_esp.o
obj-$(CONFIG_SCSI_MESH)		+= mesh.o
obj-$(CONFIG_SCSI_MAC53C94)	+= mac53c94.o
obj-$(CONFIG_BLK_DEV_3W_XXXX_RAID) += 3w-xxxx.o
obj-$(CONFIG_SCSI_3W_9XXX)	+= 3w-9xxx.o
obj-$(CONFIG_SCSI_PPA)		+= ppa.o
obj-$(CONFIG_SCSI_IMM)		+= imm.o
obj-$(CONFIG_JAZZ_ESP)		+= esp_scsi.o	jazz_esp.o
obj-$(CONFIG_SUN3X_ESP)		+= esp_scsi.o	sun3x_esp.o
obj-$(CONFIG_SCSI_LASI700)	+= 53c700.o lasi700.o
obj-$(CONFIG_SCSI_SNI_53C710)	+= 53c700.o sni_53c710.o
obj-$(CONFIG_SCSI_NSP32)	+= nsp32.o
obj-$(CONFIG_SCSI_IPR)		+= ipr.o
obj-$(CONFIG_SCSI_SRP)		+= libsrp.o
obj-$(CONFIG_SCSI_HPTIOP)	+= hptiop.o
obj-$(CONFIG_SCSI_STEX)		+= stex.o
obj-$(CONFIG_SCSI_MVSAS)	+= mvsas.o
obj-$(CONFIG_PS3_ROM)		+= ps3rom.o

obj-$(CONFIG_CHR_DEV_ST)	+= st.o
obj-$(CONFIG_CHR_DEV_OSST)	+= osst.o
obj-$(CONFIG_BLK_DEV_SD)	+= sd_mod.o
obj-$(CONFIG_BLK_DEV_SR)	+= sr_mod.o
obj-$(CONFIG_CHR_DEV_SG)	+= sg.o
obj-$(CONFIG_CHR_DEV_SCH)	+= ch.o
obj-$(CONFIG_SCSI_ENCLOSURE)	+= ses.o

# This goes last, so that "real" scsi devices probe earlier
obj-$(CONFIG_SCSI_DEBUG)	+= scsi_debug.o

obj-$(CONFIG_SCSI_WAIT_SCAN)	+= scsi_wait_scan.o

scsi_mod-y			+= scsi.o hosts.o scsi_ioctl.o constants.o \
				   scsicam.o scsi_error.o scsi_lib.o
scsi_mod-$(CONFIG_SCSI_DMA)	+= scsi_lib_dma.o
scsi_mod-y			+= scsi_scan.o scsi_sysfs.o scsi_devinfo.o
scsi_mod-$(CONFIG_SCSI_NETLINK)	+= scsi_netlink.o
scsi_mod-$(CONFIG_SYSCTL)	+= scsi_sysctl.o
scsi_mod-$(CONFIG_SCSI_PROC_FS)	+= scsi_proc.o

scsi_tgt-y			+= scsi_tgt_lib.o scsi_tgt_if.o

sd_mod-objs	:= sd.o
sd_mod-$(CONFIG_BLK_DEV_INTEGRITY) += sd_dif.o

sr_mod-objs	:= sr.o sr_ioctl.o sr_vendor.o yy_cd.o
ncr53c8xx-flags-$(CONFIG_SCSI_ZALON) \
		:= -DCONFIG_NCR53C8XX_PREFETCH -DSCSI_NCR_BIG_ENDIAN \
			-DCONFIG_SCSI_NCR53C8XX_NO_WORD_TRANSFERS
CFLAGS_ncr53c8xx.o	:= $(ncr53c8xx-flags-y) $(ncr53c8xx-flags-m)
zalon7xx-objs	:= zalon.o ncr53c8xx.o
NCR_Q720_mod-objs	:= NCR_Q720.o ncr53c8xx.o
oktagon_esp_mod-objs	:= oktagon_esp.o oktagon_io.o

# Files generated that shall be removed upon make clean
clean-files :=	53c700_d.h 53c700_u.h

$(obj)/53c700.o $(MODVERDIR)/$(obj)/53c700.ver: $(obj)/53c700_d.h

# If you want to play with the firmware, uncomment
# GENERATE_FIRMWARE := 1

ifdef GENERATE_FIRMWARE

$(obj)/53c700_d.h: $(src)/53c700.scr $(src)/script_asm.pl
	$(PERL) -s $(src)/script_asm.pl -ncr7x0_family $@ $(@:_d.h=_u.h) < $<

endif
