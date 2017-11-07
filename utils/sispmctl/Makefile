#
# Copyright (C) 2008-2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=sispmctl
PKG_VERSION:=4.0+20160327
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=064850d6246d5342214d8b304fe22e09c925a421
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_MIRROR_HASH:=a0a6d1b2c5402ac781d2dbfa804933ce8f83ea0a95f25811240e94e107703472
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=git://git.code.sf.net/p/sispmctl/git
PKG_MAINTAINER:=Richard Kunze <richard.kunze@web.de>
PKG_LICENSE:=GPL-2.0+

PKG_INSTALL:=1
PKG_FIXUP:=autoreconf

include $(INCLUDE_DIR)/package.mk

define Package/sispmctl
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Silver Shield PM Control for Linux
  URL:=http://sispmctl.sourceforge.net/
  DEPENDS:=+libusb-compat
endef

define Package/sispmctl/description
 The sispmctl tool can control Gembird SIS-PM Silver Shield
 programmable power outlet strips (also known under the name
 Revolt Intelli-Plug) from the command line.
 .
 It can be used to switch on or off any of the programmable
 power sockets of the SIS-PM via USB. It can also show the
 current status of each power socket, and it can handle
 multiple SIS-PM devices, too.
endef

TARGET_CFLAGS += -D_GNU_SOURCE
CONFIGURE_ARGS += \
	--enable-webless \
	--disable-dependency-tracking

define Package/sispmctl/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/$(PKG_NAME) $(1)/usr/bin/
endef

$(eval $(call BuildPackage,sispmctl))
