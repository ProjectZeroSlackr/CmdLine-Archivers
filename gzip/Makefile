# Gzip for the ipod.
#
# Cleaned this makefile up quite a bit..WHY do people insist on using GNU's makefile tools?!
#
# Anyway, use this like the normal gzip. Becuase it is.

srcdir = .
VPATH = .

CC = arm-uclinux-elf-gcc

DEFS = -DSTDC_HEADERS=1 -DHAVE_UNISTD_H=1 -DDIRENT=1

OBJA =

SEDCMD = 

CFLAGS = -O -Wl,-elf2flt
LDFLAGS = $(CFLAGS)

O=.o

SRCS = gzip.c zip.c deflate.c trees.c bits.c unzip.c inflate.c util.c crypt.c\
       lzw.c unlzw.c unpack.c unlzh.c getopt.c

OBJS = gzip$O zip$O deflate$O trees$O bits$O unzip$O inflate$O util$O \
       crypt$O lzw$O unlzw$O unpack$O unlzh$O getopt$O $(OBJA)

HDRS = gzip.h lzw.h tailor.h revision.h crypt.h getopt.h

.c$O:
	$(CC) -c $(DEFS) $(CFLAGS) $<

default:  gzip	
all:	gzip

clean:
	rm -f *$O gzip gzip.gdb

gzip: $(OBJS)
	$(CC) $(LDFLAGS) -o $@ $(OBJS) $(LIBS)
