#
# Copyright (C) 2017 Yousong Zhou <yszhou4tech@gmail.com>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

BOARD:=ps225
BOARDNAME:=PS225 Stingray
FEATURES:=fpu pci rtc usb
FEATURES+=cpiogz ext4 ramdisk squashfs targz
MAINTAINER:=samik.gupta@broadcom.com

KERNEL_PATCHVER:=4.14

include $(INCLUDE_DIR)/target.mk

$(eval $(call BuildTarget))
