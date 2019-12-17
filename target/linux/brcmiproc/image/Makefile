#
# Copyright (C) 2016-2017 Yousong Zhou <yszhou4tech@gmail.com>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/image.mk

define Device/Default
  DEVICE_DTS_DIR := $(DTS_DIR)/broadcom
endef

define Device/bcm958802a802x
  DEVICE_DTS := stingray/bcm958802a802x
endef
TARGET_DEVICES += bcm958802a802x

define Image/BuildKernel
	$(foreach k,$(filter zImage Image,$(KERNELNAME)), \
		cp $(KDIR)/$(KERNELNAME) $(BIN_DIR)/$(IMG_PREFIX)-$(k) \
	)
	$(foreach d,$(TARGET_DEVICES),cp $(KDIR)/image-$(d).dtb $(BIN_DIR);)
endef

define Image/Build/Initramfs
	$(foreach k,$(filter zImage Image,$(KERNELNAME)), \
		cp $(KDIR)/$(k)-initramfs $(BIN_DIR)/$(IMG_PREFIX)-$(k)-initramfs \
	)
endef

define Image/Build
	$(call Image/Build/$(1))
	dd if=$(KDIR)/root.$(1) bs=128k conv=sync | \
		gzip -9n >$(BIN_DIR)/$(IMG_PREFIX)-root.$(1).gz
endef

$(eval $(call BuildImage))
