# 
# Copyright (C) 2006-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=quilt
PKG_VERSION:=0.65

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=@SAVANNAH/quilt
PKG_MD5SUM:=c67ba0228f5b7b8bbe469474661f92d6

include $(INCLUDE_DIR)/host-build.mk

define Host/Configure
	cd $(HOST_BUILD_DIR) && autoconf
	$(call Host/Configure/Default)
	[ -f $(HOST_BUILD_DIR)/Makefile ]
endef

define Host/Compile
	$(MAKE) -C $(HOST_BUILD_DIR) SHELL="$(BASH)" all
endef

define Host/Install
	$(MAKE) -C $(HOST_BUILD_DIR) SHELL="$(BASH)" install
endef

define Host/Clean
	rm -f $(STAGING_DIR_HOST)/bin/quilt
endef

$(eval $(call HostBuild))
