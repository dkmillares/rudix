BuildRequires += $(LibDir)/libintl.la
BuildRequires += $(BinDir)/msgfmt

include ../../Library/Unix.mk

Title=		Dos2Unix
Name=		dos2unix
Version=	7.3.4
Site=		http://waterlan.home.xs4all.nl/dos2unix.html
Source=		http://waterlan.home.xs4all.nl/dos2unix//$(Name)-$(Version).tar.gz
License=	BSD

ReadMeFile=	$(SourceDir)/README.txt
LicenseFile=	$(SourceDir)/COPYING.txt

MakeInstallExtra += prefix=$(Prefix) docsubdir=dos2unix

ifeq ($(RUDIX_BUILD_WITH_STATIC_LIBS),yes)
LdFlags = $(ArchFlags) /usr/local/lib/libintl.a -liconv -framework CoreFoundation
endif

define test_hook
endef

define test_hook
$(BinDir)/dos2unix -V
$(BinDir)/unix2dos -V
endef
