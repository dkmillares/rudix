BuildRequires += $(BinDir)/pcre-config

include ../../Library/GNU.mk

Title=		Apache HTTPd
Name=		httpd
Version=	2.4.2
Site=		http://httpd.apache.org/
Source=		http://ftp.unicamp.br/pub/apache//httpd//$(Name)-$(Version).tar.bz2
License=	Apache

LicenseFile=	$(SourceDir)/LICENSE

GnuConfigureExtra += --enable-layout=Rudix
StripExtra += -x # Due `Symbol not found' error

define install_post_hook
for x in httpd.conf magic mime.types ; do \
	mv $(InstallDir)/$(SysConfDir)/apache2/$$x $(InstallDir)/$(SysConfDir)/apache2/$$x.default ; \
done
for x in $(InstallDir)/$(SysConfDir)/apache2/extra/*.conf ; do \
	mv $$x $$x.default ; \
done
mv $(InstallDir)/$(LocalStateDir)/www/html/index.html $(InstallDir)/$(LocalStateDir)/www/html/index.html.default
endef
