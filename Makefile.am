ACLOCAL_AMFLAGS := -I m4

AM_CFLAGS := -Wundef \
        -Wstrict-prototypes \
        -Wno-trigraphs \
        -g -O0 \
        $(LOCBASEUTIL_CFLAGS) \
        -fno-inline \
        -fno-short-enums \
        -fpic \
        -D_GNU_SOURCE \
        -DHAVE_CONFIG_H=1 \
        -DBUILD_DIVSUFSORT64 \
        -I..

AM_CPPFLAGS := \
              -I. \
              -I$(WORKSPACE)/OTA/streaming/external/libchrome \
              -D_FILE_OFFSET_BITS=64 \
              -D_USE_RTTI_FOR_TYPE_TAGS \
              -DUSE_LE_MODE \
              -std=c++11

AUTOMAKE_OPTIONS = subdir-objects

AM_LDFLAGS := -shared -version-info 1:0:0


libmodpb64_src_la_SOURCES := modp_b64.cc

library_includedir := $(pkgincludedir)

lib_LTLIBRARIES := libmodpb64.la
libmodpb64_la_SOURCES := $(libmodpb64_src_la_SOURCES)


if USE_GLIB
libmodpb64_la_CFLAGS := $(AM_CFLAGS) -DUSE_GLIB @GLIB_CFLAGS@
libmodpb64_la_CPPFLAGS := $(AM_CPPFLAGS) -fpermissive -DUSE_GLIB @GLIB_CFLAGS@
else
libmodpb64_la_CFLAGS := $(AM_CFLAGS)
libmodpb64_la_CPPFLAGS := $(AM_CPPFLAGS) -fpermissive
endif

