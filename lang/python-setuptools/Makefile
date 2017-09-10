#
# Copyright (C) 2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
# 

include $(TOPDIR)/rules.mk

PKG_NAME:=python-setuptools
PKG_VERSION:=36.2.7
PKG_RELEASE:=1

PKG_SOURCE:=setuptools-$(PKG_VERSION).zip
PKG_SOURCE_URL:=https://pypi.python.org/packages/07/a0/11d3d76df54b9701c0f7bf23ea9b00c61c5e14eb7962bb29aed866a5844e
PKG_MD5SUM:=b9e6c049617bac0f9e908a41ab4a29ac

PKG_BUILD_DIR:=$(BUILD_DIR)/setuptools-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-setuptools
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Tool for installing Python packages.
  URL:=https://bitbucket.org/pypa/setuptools
  DEPENDS:=+python
endef

define Package/python-setuptools/description
  Easily download, build, install, upgrade, and uninstall Python packages
endef

define Build/Compile
	$(call Build/Compile/PyMod,,\
		install --prefix="$(PKG_INSTALL_DIR)/usr" \
	)
endef

define Build/InstallDev
	$(INSTALL_DIR) $(PYTHON_LIB_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(PYTHON_LIB_DIR)
endef

define PyPackage/python-setuptools/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin/
endef

$(eval $(call PyPackage,python-setuptools))
$(eval $(call BuildPackage,python-setuptools))

