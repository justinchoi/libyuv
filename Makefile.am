SUBDIRS = source

EXTRA_DIST = AUTHORS DEPS LICENSE PATENTS README.chromium codereview.settings libyuv.gyp libyuv_test.gyp unit_test/testdata/arm_v7.txt unit_test/testdata/tegra3.txt util/compare.cc

if WITH_TEST

TESTS = unittest

noinst_PROGRAMS = $(TESTS)

unittest_SOURCES = unit_test/basictypes_test.cc \
		   unit_test/compare_test.cc \
		   unit_test/convert_test.cc \
		   unit_test/cpu_test.cc \
		   unit_test/planar_test.cc \
		   unit_test/rotate_argb_test.cc \
		   unit_test/rotate_test.cc \
		   unit_test/scale_argb_test.cc \
		   unit_test/scale_test.cc \
		   unit_test/unit_test.cc \
		   unit_test/unit_test.h \
		   unit_test/version_test.cc \
		   unit_test/video_common_test.cc

unittest_CXXFLAGS = $(AM_CXXFLAGS) @GTEST_CXXFLAGS@ -I$(top_srcdir)/include -I$(top_srcdir)
unittest_LDADD = @GTEST_LIBS@ $(top_builddir)/source/libyuv.la

endif
