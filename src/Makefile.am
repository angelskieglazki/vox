if DEBUG
  AM_CFLAGS =-I$(top_srcdir)/cdk/include -Wall -g -O3
else
  AM_CFLAGS =-I$(top_srcdir)/cdk/include -Wall
endif

# Our binary is produced here
bin_PROGRAMS = vox
vox_SOURCES = main.c

# noinst_ : assures that this library is not installed to the user's computer
# libBLAH.a is a Unix convention. If you noticed, we replaced the . with _ in SOURCES line.
vox_LDADD = ../cdk/libcdk.a
LIBS = -lncurses