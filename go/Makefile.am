EXTRA_DIST = \
	heif/heif.go

gopath:
	ln -sf ${CURDIR} ${CURDIR}/src

if HAVE_GO
test-go: gopath $(top_builddir)/libheif/libheif.la $(top_builddir)/libheif.pc
	GOPATH=${CURDIR} PKG_CONFIG_PATH=$(abs_top_builddir) CGO_CFLAGS="-I$(abs_top_builddir)" CGO_LDFLAGS="-L$(abs_top_builddir)/libheif/.libs" LD_LIBRARY_PATH=$(abs_top_builddir)/libheif/.libs $(GO) test -v heif
else
test-go:
	echo ""go" not present in "${PATH}", skipping tests"
endif

test-local: test-go
