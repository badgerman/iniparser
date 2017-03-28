#
# iniparser tests Makefile
#

CC      = gcc
CFLAGS  = -g -I../src -Wall
LFLAGS  = -L.. -liniparser
AR	    = ar
ARFLAGS = rcv
RM      = rm -f
EXAMPLES = iniexample parse inifile

default: all

all: $(EXAMPLES)

%: %.c
	$(CC) $(CFLAGS) -o $@ $< -I../src -L.. -liniparser

clean veryclean:
	$(RM) $(EXAMPLES) example.ini



