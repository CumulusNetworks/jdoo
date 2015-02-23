# Additional flags to pass to aclocal when it is invoked automatically at
# make time. This allows libtool to install its m4 macros.
# The ${ACLOCAL_FLAGS} variable is picked up from the environment
# to provide a way for the user to supply additional arguments.
ACLOCAL_AMFLAGS = -I m4 --install ${ACLOCAL_FLAGS}


# Grammar files
GRAMMAR		= p.y l.l
GRAMMAR_C	= p.c l.c
GRAMMAR_H	= p.h

# Source Files
HFILES		= \
		file.h      \
		protocols/protocol.h      \
		net.h      \
		event.h      \
		md5.h      \
		state.h      \
		ssl.h      \
		sha.h      \
		process.h      \
		alert.h      \
		http/cervlet.h      \
		http/base64.h      \
		http/engine.h      \
		http/processor.h      \
		http/httpstatus.h      \
		socket.h      \
		process/process_sysdep.h      \
		util.h      \
		device/device.h      \
		device/device_sysdep.h      \
		monitor.h
CFILES		= \
		log.c      \
		protocols/clamav.c      \
		protocols/generic.c      \
		protocols/apache_status.c      \
		protocols/ldap2.c      \
		protocols/pop.c      \
		protocols/dwp.c      \
		protocols/ssh.c      \
		protocols/nntp.c      \
		protocols/lmtp.c      \
		protocols/default.c      \
		protocols/protocol.c      \
		protocols/ntp3.c      \
		protocols/imap.c      \
		protocols/smtp.c      \
		protocols/memcache.c      \
		protocols/sip.c      \
		protocols/ftp.c      \
		protocols/pgsql.c      \
		protocols/rdate.c      \
		protocols/tns.c      \
		protocols/radius.c      \
		protocols/rsync.c      \
		protocols/ldap3.c      \
		protocols/mysql.c      \
		protocols/postfix_policy.c      \
		protocols/http.c      \
		protocols/dns.c      \
		protocols/gps.c      \
		xmalloc.c      \
		process.c      \
		gc.c      \
		state.c      \
		xml.c      \
		net.c      \
		spawn.c      \
		util.c      \
		event.c      \
		control.c      \
		collector.c      \
		env.c      \
		status.c      \
		sendmail.c      \
		socket.c      \
		signal.c      \
		validate.c      \
		http/cervlet.c      \
		http/processor.c      \
		http/engine.c      \
		http/base64.c      \
		file.c      \
		sha.c      \
		monitor.c      \
		process/process_common.c      \
		daemonize.c      \
		device/device_common.c      \
		alert.c      \
		ssl.c      \
		http.c      \
		md5.c

man_MANS	= jdoo.1
AM_YFLAGS	= -d -v -t
AM_LFLAGS	= -i
bin_PROGRAMS	= jdoo
jdoo_CPPFLAGS = \
		-I. -I$(top_srcdir)/device \
		-I$(top_srcdir)/http -I$(top_srcdir)/process \
		-I$(top_srcdir)/protocols \
		-D$(ARCH) -DSYSCONFDIR="\"$(sysconfdir)\""
jdoo_SOURCES = \
		$(GRAMMAR) $(HFILES) $(CFILES)   \
		device/sysdep_LINUX.c          \
		process/sysdep_LINUX.c

if USE_STRFTIME
    jdoo_SOURCES += external/strftime.c
endif

# Additional things to distribute
EXTRA_DIST	= $(top_srcdir)/.version
BUILT_SOURCES	= $(top_srcdir)/.version \
			$(GRAMMAR_H)

# Additional make rules
# ===============================================
$(top_srcdir)/.version:
	echo "$(PACKAGE_VERSION)" > $@-t && mv $@-t $@
dist-hook:
	echo "$(PACKAGE_VERSION)" > $(distdir)/$(TARBALL_VERSION_FILE)
