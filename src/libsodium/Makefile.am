lib_LTLIBRARIES = \
	libsodium.la

libsodium_la_SOURCES = \
	crypto_core/salsa20/ref/core_salsa20.c \
	crypto_core/salsa20/core_salsa20_api.c \
	crypto_core/salsa20/ref/api.h \
	crypto_stream/chacha20/stream_chacha20_api.c \
	crypto_stream/chacha20/ref/api.h \
	crypto_stream/chacha20/ref/stream_chacha20_ref.c \
	crypto_stream/salsa20/stream_salsa20_api.c \
	sodium/utils.c \
	sodium/version.c

libsodium_la_SOURCES += \
	crypto_stream/salsa20/ref/api.h \
	crypto_stream/salsa20/ref/stream_salsa20_ref.c \
	crypto_stream/salsa20/ref/xor_salsa20_ref.c

libsodium_la_LDFLAGS = \
	$(AM_LDFLAGS) \
	-export-dynamic \
	-no-undefined \
	$(LIBTOOL_EXTRA_FLAGS)

libsodium_la_CPPFLAGS = \
	$(LTDLINCL) \
	-I$(srcdir)/include/sodium \
	-I$(builddir)/include/sodium

if HAVE_LD_OUTPUT_DEF
libsodium_la_LDFLAGS += -Wl,--output-def,libsodium-$(DLL_VERSION).def
defexecdir = $(bindir)
defexec_DATA = libsodium-$(DLL_VERSION).def
CLEANFILES = $(defexec_DATA)
libsodium-$(DLL_VERSION).def: libsodium.la
endif

SUBDIRS = \
	include
