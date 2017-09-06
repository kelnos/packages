#
# Copyright (C) 2009-2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=intltool
PKG_LIBVER:=0.51
PKG_VERSION:=$(PKG_LIBVER).0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://launchpad.net/intltool/trunk/$(PKG_VERSION)/+download
PKG_MD5SUM:=12e517cac2b57a0121cda351570f1e63
PKG_MAINTAINER:=Ted Hess <thess@kitschensync.net>

PKG_HOST_ONLY:=1

include $(INCLUDE_DIR)/host-build.mk
include $(INCLUDE_DIR)/package.mk

define Package/intltool
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:=set of tools to centralize translation using GNU gettext
  URL:=http://www.freedesktop.org/wiki/Software/intltool
  BUILDONLY:=1
endef

define Package/intltool/description
  intltool is a set of tools to centralize translation of many different
  file formats using GNU gettext-compatible PO files.
endef

define Require/perl-xml-parser
  perl -e 'use XML::Parser;'
endef

$(eval $(call Require,perl-xml-parser, \
	Please install Perl XML::Parser \
))

$(eval $(call BuildPackage,intltool))
$(eval $(call HostBuild))
