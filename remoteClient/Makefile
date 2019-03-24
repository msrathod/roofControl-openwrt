include $(TOPDIR)/rules.mk

PKG_NAME:=remoteClient
PKG_VERSION:=0.1.0
PKG_RELEASE:=1

PKG_MAINTAINER:=Mohit Rathod
PKG_LICENSE:=MIT

PKG_BUILD_PARALLEL:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git://github.com/msrathod/roofControl.git
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz

include $(INCLUDE_DIR)/uclibc++.mk
include $(INCLUDE_DIR)/package.mk

define Package/remoteClient
  SUBMENU:=Lambda
  SECTION:=net
  CATEGORY:=Network
  TITLE:=IR remote Client for IOT RetRoof
  URL:=http://www.blynk.cc
  DEPENDS:=+libpthread +librt $(CXX_DEPENDS)
endef

define Package/remoteClient/description
 This is an IR remote handler and client to the roofControl server.
 Adds support for the sparkfun IR remote to the Onion Omega 2/2+ 
 SOCs.
endef

MAKE_PATH:=remoteClient

MAKE_FLAGS += LD="$(TARGET_CXX)"

define Package/remoteClient/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/remoteClient/remoteClient $(1)/usr/bin/
endef

$(eval $(call BuildPackage,remoteClient))
