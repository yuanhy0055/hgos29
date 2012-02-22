#
# Makefile for the linux networking.
#
# 2 Sep 2000, Christoph Hellwig <hch@infradead.org>
# Rewritten to use lists instead of if-statements.
#

obj-y	:= nonet.o

obj-$(CONFIG_NET)		:= socket.o core/

tmp-$(CONFIG_COMPAT) 		:= compat.o
obj-$(CONFIG_NET)		+= $(tmp-y)

# LLC has to be linked before the files in net/802/
obj-$(CONFIG_LLC)		+= llc/
obj-$(CONFIG_NET)		+= ethernet/ 802/ sched/ netlink/
obj-$(CONFIG_NETFILTER)		+= netfilter/
obj-$(CONFIG_INET)		+= ipv4/
obj-$(CONFIG_XFRM)		+= xfrm/
obj-$(CONFIG_UNIX)		+= unix/
obj-$(CONFIG_PACKET)		+= packet/
obj-$(CONFIG_NET_KEY)		+= key/
obj-$(CONFIG_NET_SCHED)		+= sched/
obj-$(CONFIG_BRIDGE)		+= bridge/
obj-$(CONFIG_WAN_ROUTER)	+= wanrouter/
obj-$(CONFIG_NETROM)		+= netrom/
obj-$(CONFIG_ROSE)		+= rose/
obj-$(CONFIG_BT)		+= bluetooth/
obj-$(CONFIG_SUNRPC)		+= sunrpc/
ifneq ($(CONFIG_VLAN_8021Q),)
obj-y				+= 8021q/
endif
obj-y				+= wireless/
obj-$(CONFIG_MAC80211)		+= mac80211/
obj-$(CONFIG_NETLABEL)		+= netlabel/
obj-$(CONFIG_RFKILL)		+= rfkill/
ifneq ($(CONFIG_DCB),)
obj-y				+= dcb/
endif

ifeq ($(CONFIG_NET),y)
obj-$(CONFIG_SYSCTL)		+= sysctl_net.o
endif
