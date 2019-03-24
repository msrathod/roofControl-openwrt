include $(TOPDIR)/rules.mk

PKG_NAME:=blynkClient
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

define Package/blynkClient
  SUBMENU:=Lambda
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Blynk Client for IOT RetRoof
  URL:=http://www.blynk.cc
  DEPENDS:=+libpthread +librt $(CXX_DEPENDS)
endef

define Package/blynkClient/description
 Blynk is a platform with iOS and Android apps to control Arduino,
 Raspberry Pi, Onion Omega and the likes over the Internet.
 You can easily build graphic interfaces for all your projects
 by simply dragging and dropping widgets.
endef

MAKE_PATH:=blynkClient

MAKE_FLAGS += LD="$(TARGET_CXX)"

define Package/blynkClient/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/blynkClient/blynkClient $(1)/usr/bin/
endef

$(eval $(call BuildPackage,blynkClient))
