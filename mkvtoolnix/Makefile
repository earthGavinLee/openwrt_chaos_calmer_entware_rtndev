#
# Copyright (C) 2011-2015 Entware
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
# A newer versions requires ruby
#

include $(TOPDIR)/rules.mk

PKG_NAME:=mkvtoolnix
PKG_VERSION:=4.2.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=http://bunkus.org/videotools/mkvtoolnix/sources
PKG_MD5SUM:=de3e99598d47d0a2226269f79faabbfd

include $(INCLUDE_DIR)/package.mk

define Package/mkvtoolnix
	SECTION:=multimedia
	CATEGORY:=Multimedia
	DEPENDS:=+boost-filesystem +boost-regex +libbz2 +libexpat +libflac \
	    +liblzo +libmagic +libmatroska +libvorbis
	TITLE:=tools for Matroska files
	URL:=http://matroska.org/
	MAINTAINER:=Entware team, entware.wl500g.info
endef

define Package/mkvtoolnix/description
 A set of tools to create, alter and inspect Matroska files.
endef

CONFIGURE_ARGS += \
	--disable-gui \
	--disable-optimization \
	--with-boost=$(STAGING_DIR)/opt \

TARGET_LDFLAGS += \
	-lstdc++ \

define Package/mkvtoolnix/install
	$(INSTALL_DIR) $(1)/opt/bin
	$(CP) $(PKG_BUILD_DIR)/src/mkv* $(1)/opt/bin
endef

$(eval $(call BuildPackage,mkvtoolnix))
