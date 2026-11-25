include $(TOPDIR)/rules.mk

PKG_NAME:=c2000max-geo-update
PKG_VERSION:=1
PKG_RELEASE:=1
PKG_LICENSE:=GPL-2.0-or-later

include $(INCLUDE_DIR)/package.mk

define Package/c2000max-geo-update
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Weekly geoip/geosite update for daed and passwall2
  DEPENDS:=+curl +ca-bundle +v2ray-geoip +v2ray-geosite
  PKGARCH:=all
endef

define Package/c2000max-geo-update/description
 Downloads the Loyalsoldier geoip.dat and geosite.dat into /usr/share/v2ray
 once a week and restarts daed when it is enabled.
endef

define Build/Compile
endef

define Package/c2000max-geo-update/install
	$(INSTALL_DIR) $(1)/usr/sbin $(1)/etc/uci-defaults
	$(INSTALL_BIN) ./files/c2000max-update-geo $(1)/usr/sbin/c2000max-update-geo
	$(INSTALL_BIN) ./files/99-c2000max-geo-update $(1)/etc/uci-defaults/99-c2000max-geo-update
endef

$(eval $(call BuildPackage,c2000max-geo-update))
