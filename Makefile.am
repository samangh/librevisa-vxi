lib_LIBRARIES = libvxiclient.a libvxiserver.a

nodist_libvxiclient_a_SOURCES = \
	vxi_clnt.c \
	vxi_intr_svr.c \
	vxi_intr_xdr.c \
	vxi_xdr.c
nodist_libvxiserver_a_SOURCES = \
	vxi_intr_clnt.c \
	vxi_intr_xdr.c \
	vxi_svr.c \
	vxi_xdr.c
nodist_include_HEADERS = \
	vxi.h \
	vxi_intr.h

BUILT_SOURCES = $(nodist_libvxiclient_a_SOURCES) $(nodist_libvxiserver_a_SOURCES) $(nodist_include_HEADERS)
CLEANFILES = $(BUILT_SOURCES)

%.h: %.x
	$(RM) $@
	rpcgen -h -o $@ $<

%_xdr.c: %.x
	$(RM) $@
	rpcgen -c -o $@ $<

%_clnt.c: %.x
	$(RM) $@
	rpcgen -l -o $@ $<

%_svr.c: %.x
	$(RM) $@
	rpcgen -m -o $@ $<

dist_noinst_DATA = vxi.x vxi_intr.x
