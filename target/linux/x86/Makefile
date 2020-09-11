#
# Copyright (C) 2006-2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

ARCH:=i386
BOARD:=x86
BOARDNAME:=x86
FEATURES:=squashfs ext4 vdi vmdk pcmcia targz fpu
SUBTARGETS:=64 generic legacy geode
MAINTAINER:=Felix Fietkau <nbd@nbd.name>

KERNEL_PATCHVER:=4.14

KERNELNAME:=bzImage

include $(INCLUDE_DIR)/target.mk

DEFAULT_PACKAGES += partx-utils mkf2fs e2fsprogs kmod-button-hotplug fdiskhtop lm-sensors luci-proto-bonding ca-certificates\
kmod-e1000e kmod-igb kmod-igbvf kmod-ixgbe kmod-vmxnet3 kmod-i40e kmod-i40evf kmod-fs-f2fs

$(eval $(call BuildTarget))

$(eval $(call $(if $(CONFIG_TARGET_ROOTFS_ISO),RequireCommand,Ignore),mkisofs, \
   	Please install mkisofs. \
))
