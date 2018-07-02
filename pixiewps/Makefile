#Contribution: part of the code was inspired by Bully by Brian Purcell
#The crypto and bignum libraries were taken from LibTomCrypt and TomsFastMath
#Endianness detection and conversion is from rofl0r/endianness.h
#See contributors for a list of everyone that has contributed
#Huge thanks to kcdtv, rofl0r and binarymaster for helping and testing
#Special thanks to soxrok2212, datahead, t6_x, aanarchyy and the Kali Linux community
#    SergarataS Openwrt fork port and maintainer
include $(TOPDIR)/rules.mk

PKG_NAME:=pixiewps
PKG_VERSION:=master

PKG_SOURCE_PROTO:=git
#PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).zip
PKG_SOURCE_URL:=https://github.com/wiire-a/pixiewps.git
PKG_MD5SUM:=75453b8646f28873de05c083a60b6a69
PKG_LICENSE:=GPL-2.0

PKG_USE_MIPS16:=0
PKG_FIXUP:=autoreconf

include $(INCLUDE_DIR)/package.mk


define Package/pixiewps
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=wireless
  TITLE:=Bruteforce offline the WPS PIN exploiting
  URL:=https://github.com/wiire-a/pixiewps.git
  DEPENDS:=reaver +reaver-wps-fork-t6x
endef

define Package/pixiewps/description
	Pixiewps is a tool written in C used to bruteforce offline the WPS PIN exploiting the low or non-existing 
	entropy of some software implementations, the so-called "pixie-dust attack" discovered by Dominique Bongard in summer 2014
	It is meant for educational purposes only.
endef

define Build/Compile
endef

define Package/pixiewps/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/sbin/pixiewps $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,pixiewps))
