include $(TOPDIR)/rules.mk

PKG_NAME:=termClient
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

define Package/termClient
  SUBMENU:=Lambda
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Bash Terminal Client for IOT RetRoof
  URL:=http://www.blynk.cc
  DEPENDS:=+libpthread +librt $(CXX_DEPENDS)
endef

define Package/termClient/description
 Bash terminal client to the roofControl server.
 Allows user to commands via terminal over ssh 
 or UART.
endef

MAKE_PATH:=termClient

MAKE_FLAGS += LD="$(TARGET_CXX)"

define Package/termClient/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/termClient/termClient $(1)/usr/bin/
endef

$(eval $(call BuildPackage,termClient))
