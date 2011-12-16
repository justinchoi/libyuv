lib_LTLIBRARIES = libyuv.la

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = libyuv.pc

libyuvincludedir = $(includedir)
libyuvnobase_includedir = $(includedir)/libyuv

if WITH_MJPEG
mjpeg_SOURCES = mjpeg_decoder.cc
mjpeg_HDRS = ../include/libyuv/mjpeg_decoder.h
endif

if LIBYUV_POSIX
posix_SOURCES = compare_posix.cc row_posix.cc
endif

if LIBYUV_WINDOWS
windows_SOURCES = compare_win.cc row_win.cc
endif

if ENABLE_MIPS
mips_SOURCES = memcpy_mips.S rotate_mips.cc row_mips.cc scale_mips.cc
endif

if ENABLE_X86
x86_SOURCES = row_x86.asm x86inc.asm
endif

if ENABLE_NEON
neon_SOURCES = compare_neon.cc rotate_neon.cc row_neon.cc scale_argb_neon.cc scale_neon.cc
endif

libyuvinclude_HEADERS = ../include/libyuv.h
libyuvnobase_include_HEADERS = ../include/libyuv/basic_types.h \
			       ../include/libyuv/compare.h \
			       ../include/libyuv/convert.h \
			       ../include/libyuv/convert_argb.h \
			       ../include/libyuv/convert_from.h \
			       ../include/libyuv/convert_from_argb.h \
			       ../include/libyuv/cpu_id.h \
			       ../include/libyuv/format_conversion.h \
			       ../include/libyuv/planar_functions.h \
			       ../include/libyuv/rotate.h \
			       ../include/libyuv/rotate_argb.h \
			       ../include/libyuv/row.h \
			       ../include/libyuv/scale.h \
			       ../include/libyuv/scale_argb.h \
			       ../include/libyuv/version.h \
			       ../include/libyuv/video_common.h \
			       $(mjpeg_HDRS)

libyuv_la_SOURCES = compare.cc \
		    compare_common.cc \
		    convert.cc \
		    convert_argb.cc \
		    convert_from.cc \
		    convert_from_argb.cc \
		    cpu_id.cc \
		    format_conversion.cc \
		    planar_functions.cc \
		    rotate.cc \
		    rotate_argb.cc \
		    row_any.cc \
		    row_common.cc \
		    scale.cc \
		    scale_argb.cc \
		    video_common.cc \
		    $(mjpeg_SOURCES) \
		    $(posix_SOURCES) \
		    $(windows_SOURCES) \
		    $(mips_SOURCES) \
		    $(neon_SOURCES) \
		    $(x86_SOURCES)

libyuv_la_CXXFLAGS = $(AM_LDFLAGS) -I$(top_srcdir)/include -I$(top_srcdir)
libyuv_la_LDFLAGS = $(AM_LDFLAGS) -version-info $(LIBYUV_VERSION_INFO)
libyuv_la_LIBADD = @LIBJPEG_LIBS@
