#
# Copyright (C) 2017 Yousong Zhou <yszhou4tech@gmail.com>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

BOARD:=brcmiproc
BOARDNAME:=Broadcom iProc SoC Family
FEATURES:=fpu pci rtc usb
FEATURES+=ext4 targz
MAINTAINER:=samik.gupta@broadcom.com

KERNEL_PATCHVER:=4.19

include $(INCLUDE_DIR)/target.mk

$(eval $(call BuildTarget))
