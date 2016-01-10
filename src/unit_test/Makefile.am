AUTOMAKE_OPTIONS=foreign subdir-objects

proj_dir = ${top_srcdir}/..
top_dir = ${proj_dir}/../..
server_rootdir = ${proj_dir}/rpc_server
util_dir = ${proj_dir}/util
ut_dir = ${proj_dir}/unit_test
third_dir = ${top_dir}/third-64

AM_CPPFLAGS = -I${proj_dir}/ \
              -I${third_dir}/gperftools/include/ \
			  -I${third_dir}/protobuf/include/ \
			  -I${third_dir}/libev/include/

#AM_LDFLAGS = -lz -lrt
AM_LDFLAGS = -lz -lstdc++

LDADD = ${third_dir}/gperftools/lib/libtcmalloc_minimal.a \
		${third_dir}/protobuf/lib/*.a \
		${third_dir}/libev/lib/*.a

RPC_SRC = ${server_rootdir}/rpc_server.h \
		  ${server_rootdir}/rpc_server.cpp \
		  ${server_rootdir}/dispatch_thread.h \
		  ${server_rootdir}/dispatch_thread.cpp \
		  ${server_rootdir}/libev_thread_pool.h \
		  ${server_rootdir}/libev_thread_pool.cpp \
		  ${util_dir}/rpc_util.h \
		  ${util_dir}/rpc_util.cpp \
		  ${util_dir}/thread.h \
		  ${util_dir}/pthread_mutex.h \
		  ${util_dir}/pthread_rwlock.h \
		  ${util_dir}/disallow_copy_and_assign.h \
		  ${util_dir}/rpc_communication.h \
		  ${util_dir}/rpc_communication.cpp

LTP = ${ut_dir}/test_libev_tp.cpp ${util_dir}/pthread_mutex.h ${server_rootdir}/libev_thread_pool.h ${server_rootdir}/libev_thread_pool.cpp

bin_PROGRAMS = ltp

ltp_SOURCES = ${LTP}

#SUBDIRS = test