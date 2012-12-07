lib_LTLIBRARIES = libvxiclient.la

nodist_libvxiclient_la_SOURCES = vxi_clnt.c \
	vxi_xdr.c
nodist_include_HEADERS = vxi.h

BUILT_SOURCES = vxi.h vxi_clnt.c vxi_xdr.c
CLEANFILES = $(BUILT_SOURCES)

%.h: %.x
	rpcgen -o $@ -h $<

%_xdr.c: %.x
	rpcgen -o $@ -c $<

%_clnt.c: %.x
	rpcgen -o $@ -l $<

dist_noinst_DATA = vxi.x
