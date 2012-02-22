#
# Makefile for the Linux kernel device drivers.
#
# 15 Sep 2000, Christoph Hellwig <hch@infradead.org>
# Rewritten to use lists instead of if-statements.
#

obj-$(CONFIG_PCI)		+= pci/
obj-y				+= video/
obj-$(CONFIG_ACPI)		+= acpi/
# PnP must come after ACPI since it will eventually need to check if acpi
# was used and do nothing if so
obj-$(CONFIG_PNP)		+= pnp/

# regulators early, since some subsystems rely on them to initialize
obj-$(CONFIG_REGULATOR)		+= regulator/

# char/ comes before serial/ etc so that the VT console is the boot-time
# default.
obj-y				+= char/
obj-y				+= firmware/

obj-$(CONFIG_CONNECTOR)		+= connector/

obj-y				+= serial/
obj-y				+= base/ block/ misc/ net/
obj-$(CONFIG_SCSI)		+= scsi/
obj-$(CONFIG_FUSION)		+= message/
obj-$(CONFIG_UIO)		+= uio/
obj-y				+= auxdisplay/
obj-$(CONFIG_PCCARD)		+= pcmcia/
obj-$(CONFIG_DIO)		+= dio/
obj-$(CONFIG_ZORRO)		+= zorro/
obj-$(CONFIG_TC)		+= tc/
obj-$(CONFIG_USB_OTG_UTILS)	+= usb/otg/
obj-$(CONFIG_USB)		+= usb/
obj-$(CONFIG_PCI)		+= usb/
obj-$(CONFIG_USB_GADGET)	+= usb/gadget/
obj-$(CONFIG_SERIO)		+= input/serio/
obj-$(CONFIG_GAMEPORT)		+= input/gameport/
obj-$(CONFIG_INPUT)		+= input/
obj-$(CONFIG_I2O)		+= message/
obj-$(CONFIG_RTC_LIB)		+= rtc/
obj-$(CONFIG_POWER_SUPPLY)	+= power/
obj-$(CONFIG_HWMON)		+= hwmon/
obj-$(CONFIG_THERMAL)		+= thermal/
obj-$(CONFIG_WATCHDOG)		+= watchdog/
obj-$(CONFIG_BT)		+= bluetooth/
obj-$(CONFIG_ACCESSIBILITY)	+= accessibility/
obj-$(CONFIG_EDAC)		+= edac/
obj-y				+= lguest/
obj-$(CONFIG_CPU_FREQ)		+= cpufreq/
obj-$(CONFIG_CPU_IDLE)		+= cpuidle/
obj-y				+= idle/
obj-$(CONFIG_NEW_LEDS)		+= leds/
obj-$(CONFIG_SGI_SN)		+= sn/
obj-$(CONFIG_CRYPTO)		+= crypto/
obj-$(CONFIG_GENERIC_TIME)	+= clocksource/
obj-$(CONFIG_DMA_ENGINE)	+= dma/
obj-$(CONFIG_DCA)		+= dca/
obj-$(CONFIG_OF)		+= of/
obj-$(CONFIG_VIRTIO)		+= virtio/
obj-y				+= platform/
