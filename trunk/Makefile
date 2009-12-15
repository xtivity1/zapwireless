#
# Zap Copyright (C) 2004-2009 Ruckus Wireless, Inc.
#

all:	bin bin/linux/zap bin/linux/zapd


CFLAGS= -O2
CC=	$(TOOLPREFIX)gcc $(CFLAGS)

bin:
	rm -f -r bin
	mkdir bin
	mkdir bin/linux

bin/linux/zap : zap/zap.c zaplib/zaplib.c zaplib/zaplib.h
	$(CC)  -o bin/linux/zap zap/zap.c zaplib/zaplib.c zaplib/error.c -Izap -Izaplib

bin/linux/zapd : zapd/zapd.c zaplib/zaplib.c zaplib/zaplib.h
	$(CC)  -o bin/linux/zapd zapd/zapd.c zaplib/zaplib.c zaplib/error.c -Izap -Izaplib 



install : bin/linux/zap 
	cp bin/linux/zap 	$(DESTDIR)/usr/bin
	cp bin/linux/zapd	$(DESTDIR)/usr/bin
	chmod +s	$(DESTDIR)/usr/bin/zap
	chmod +s	$(DESTDIR)/usr/bin/zapd

clean :
	rm -f -r bin
