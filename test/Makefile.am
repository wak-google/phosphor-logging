AM_CPPFLAGS = -I${top_srcdir}

TESTS = $(check_PROGRAMS)

check_PROGRAMS = \
	elog_errorwrap_test \
	serialization_test_path \
	serialization_test_properties \
	remote_logging_test_address \
	remote_logging_test_port \
	remote_logging_test_config \
	sdjournal_mock_test

test_cppflags = \
	-Igtest \
	$(GTEST_CPPFLAGS) \
	$(AM_CPPFLAGS) \
	$(PHOSPHOR_DBUS_INTERFACES_CFLAGS) \
	$(SDBUSPLUS_CFLAGS)

test_cxxflags = \
	$(PTHREAD_CFLAGS)

test_ldflags = \
	-lgtest_main -lgtest \
	-lgmock \
	$(PTHREAD_LIBS) \
	$(OESDK_TESTCASE_FLAGS) \
	$(PHOSPHOR_DBUS_INTERFACES_LIBS) \
	$(SDBUSPLUS_LIBS)

test_ldadd = \
	$(top_builddir)/elog_serialize.o \
	$(top_builddir)/elog_entry.o \
	$(top_builddir)/log_manager.o \
	$(top_builddir)/org.openbmc.Associations.o \
	$(top_builddir)/xyz/openbmc_project/Logging/Internal/Manager/server.o \
	$(top_builddir)/elog_meta.o \
	$(top_builddir)/elog-lookup.o \
	$(top_builddir)/elog-process-metadata.o \
	$(top_builddir)/sdjournal.o

remote_logging_test_ldadd = \
	$(top_builddir)/phosphor-rsyslog-config/server-conf.o \
	$(top_builddir)/sdjournal.o

elog_errorwrap_test_CPPFLAGS = $(test_cppflags)
elog_errorwrap_test_CXXFLAGS = $(test_cxxflags)
elog_errorwrap_test_SOURCES = elog_errorwrap_test.cpp
elog_errorwrap_test_LDADD = $(test_ldadd)
elog_errorwrap_test_LDFLAGS = \
        $(test_ldflags) \
        -lstdc++fs

serialization_test_path_CPPFLAGS = $(test_cppflags)
serialization_test_path_CXXFLAGS = $(test_cxxflags)
serialization_test_path_SOURCES = serialization_test_path.cpp
serialization_test_path_LDADD = $(test_ldadd)
serialization_test_path_LDFLAGS = \
	$(test_ldflags) \
	-lstdc++fs

serialization_test_properties_CPPFLAGS = $(test_cppflags)
serialization_test_properties_CXXFLAGS = $(test_cxxflags)
serialization_test_properties_SOURCES = serialization_test_properties.cpp
serialization_test_properties_LDADD = $(test_ldadd)
serialization_test_properties_LDFLAGS = \
	$(test_ldflags) \
	-lstdc++fs

remote_logging_test_address_CPPFLAGS = $(test_cppflags)
remote_logging_test_address_CXXFLAGS = $(test_cxxflags)
remote_logging_test_address_SOURCES = remote_logging_test_address.cpp
remote_logging_test_address_LDADD = $(remote_logging_test_ldadd)
remote_logging_test_address_LDFLAGS = \
	$(test_ldflags) \
	-lstdc++fs

remote_logging_test_port_CPPFLAGS = $(test_cppflags)
remote_logging_test_port_CXXFLAGS = $(test_cxxflags)
remote_logging_test_port_SOURCES = remote_logging_test_port.cpp
remote_logging_test_port_LDADD = $(remote_logging_test_ldadd)
remote_logging_test_port_LDFLAGS = \
	$(test_ldflags) \
	-lstdc++fs

remote_logging_test_config_CPPFLAGS = $(test_cppflags)
remote_logging_test_config_CXXFLAGS = $(test_cxxflags)
remote_logging_test_config_SOURCES = remote_logging_test_config.cpp
remote_logging_test_config_LDADD = $(remote_logging_test_ldadd)
remote_logging_test_config_LDFLAGS = \
	$(test_ldflags) \
	-lstdc++fs

sdjournal_mock_test_CPPFLAGS = $(test_cppflags)
sdjournal_mock_test_CXXFLAGS = $(test_cxxflags)
sdjournal_mock_test_SOURCES = sdtest.cpp
sdjournal_mock_test_LDADD = $(top_builddir)/sdjournal.o
sdjournal_mock_test_LDFLAGS = $(test_ldflags)

# TODO Remove once the test-case failure is resolved openbmc/phosphor-logging#11
XFAIL_TESTS = elog_errorwrap_test
