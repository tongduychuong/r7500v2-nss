include $(TOPDIR)/rules.mk

PKG_NAME:=r8126
<<<<<<< HEAD
PKG_VERSION:=10.015.00
PKG_RELEASE:=3

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=https://github.com/openwrt/rtl8126/releases/download/$(PKG_VERSION)
PKG_HASH:=fac513aa925264a95b053e7532fcda56022d29db288f6625fafee2759a8a6124
=======
PKG_VERSION:=10.014.01
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=https://github.com/openwrt/rtl8126/releases/download/$(PKG_VERSION)
PKG_HASH:=dbb10a7abd0972e4abd1b89ea4eb22fc55d6c1dc2f711b5acf4a3bc376275e21
>>>>>>> d08eedd536 (ipq806x-nss)

PKG_BUILD_PARALLEL:=1
PKG_LICENSE:=GPLv2
PKG_MAINTAINER:=Alvaro Fernandez Rojas <noltari@gmail.com>

include $(INCLUDE_DIR)/kernel.mk
include $(INCLUDE_DIR)/package.mk

define KernelPackage/r8126
  SUBMENU:=Network Devices
  TITLE:=Realtek RTL8126 PCI 5 Gigabit Ethernet driver
  DEPENDS:=@PCI_SUPPORT +kmod-libphy
  FILES:=$(PKG_BUILD_DIR)/src/r8126.ko
<<<<<<< HEAD
  AUTOLOAD:=$(call AutoProbe,r8126,1)
=======
  AUTOLOAD:=$(call AutoProbe,r8126)
>>>>>>> d08eedd536 (ipq806x-nss)
  PROVIDES:=kmod-r8169
  VARIANT:=regular
endef

define KernelPackage/r8126-rss
$(call KernelPackage/r8126)
  CONFLICTS:=kmod-r8126
  TITLE+= (RSS)
  VARIANT:=rss
endef

ifeq ($(BUILD_VARIANT),rss)
<<<<<<< HEAD
  PKG_MAKE_FLAGS += \
    ENABLE_MULTIPLE_TX_QUEUE=y \
    ENABLE_RSS_SUPPORT=y
=======
  PKG_MAKE_FLAGS += ENABLE_RSS_SUPPORT=y
>>>>>>> d08eedd536 (ipq806x-nss)
endif

define Build/Compile
	+$(KERNEL_MAKE) $(PKG_JOBS) \
		$(PKG_MAKE_FLAGS) \
		M="$(PKG_BUILD_DIR)/src" \
		modules
endef

$(eval $(call KernelPackage,r8126))
$(eval $(call KernelPackage,r8126-rss))
