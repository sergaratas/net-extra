#Contribution: Creator of reaver-wps-fork-t6x "community edition": t6x
#Main developer since version 1.6b: rofl0r
#Modifications made by: t6_x, DataHead, Soxrok2212, Wiire, AAnarchYY, kib0rg, KokoSoft, rofl0r, horrorho, binarymaster, Ǹotaz
#Some ideas made by: nuroo, kcdtv
#Bug fixes made by: alxchk, USUARIONUEVO, ldm314, vk496, falsovsky, rofl0r, xhebox
#Special Thanks
#    Soxrok2212 for all work done to help in the development of tools
#    Wiire for developing Pixiewps
#    Craig Heffner for creating Reaver and for the creation of default pin generators (D-Link, Belkin) - http://www.devttys0.com/
#    Dominique Bongard for discovering the Pixie Dust attack.
#    SergarataS Openwrt fork port and maintainer
include $(TOPDIR)/rules.mk

PKG_NAME:=reaver-wps-fork-t6x
PKG_VERSION:=master

PKG_SOURCE_PROTO:=git
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).zip
PKG_SOURCE_URL:=https://github.com/t6x/reaver-wps-fork-t6x.git
PKG_MD5SUM:=b2b5dbdb255407166089db712b6d49bd
PKG_LICENSE:=GPL-2.0

PKG_USE_MIPS16:=0
PKG_AUTOMAKE_PATHS:=src
PKG_FIXUP:=autoreconf

include $(INCLUDE_DIR)/package.mk

CONFIGURE_PATH:=src
MAKE_PATH:=src

define Package/reaver-wps-fork-t6x
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=wireless
  TITLE:=Efficient brute force attack against Wifi Protected Setup
  URL:=https://github.com/t6x/reaver-wps-fork-t6x.git
  DEPENDS:=+libpcap +libsqlite3 +pixiewps reaver
#  CONFIGURE_ARGS +=--disable-reaver

endef

define Package/reaver-wps-fork-t6x/description
  reaver-wps-fork-t6x targets the external registrar functionality mandated by the WiFi
  Protected Setup specification.
  Access points will provide authenticated registrars with their current
  wireless configuration (including the WPA PSK), and also accept a new
  configuration from the registrar.
endef

define Package/reaver-wps-fork-t6x/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/{reaver,wash} $(1)/usr/bin/
	$(INSTALL_DIR) $(1)/etc/reaver
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/src/reaver.db $(1)/etc/reaver/
endef

$(eval $(call BuildPackage,reaver))
