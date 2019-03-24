include $(TOPDIR)/rules.mk

PKG_NAME:=roofManager
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

#define Build/Prepare
#	mkdir -p $(PKG_BUILD_DIR)
#	$(CP) -r /data2/Projects/blynk-library-arduino/* $(PKG_BUILD_DIR)/
#endef

define Package/roofManager
  SUBMENU:=Lambda
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Roof Server for IOT RetRoof
  URL:=http://www.blynk.cc
  DEPENDS:=+libpthread +librt $(CXX_DEPENDS)
endef

define Package/roofManager/description
 Roof server and manager. Package serves as a command
 parser as well as a server for various clients. 
endef

MAKE_PATH:=roofManager

MAKE_FLAGS += LD="$(TARGET_CXX)"

define Package/roofManager/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/roofManager/roofManager $(1)/usr/bin/
endef

$(eval $(call BuildPackage,roofManager))
