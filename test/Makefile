DEFS = -fhost -fdynamic-calls -std=c99

COPRTHR = /usr/local/browndeer/coprthr2

INCS = -I. -I$(COPRTHR)/include
LIBS = -L$(COPRTHR)/lib -lcoprthr2_dev -lcoprthr_hostcall -lesyscall -le-lib
LIBS += -L../src/ -lshmem
INCS += -I../src/

SRC_FILES = $(wildcard *.c)

DEPENDS = ctimer.o

TARGETS = \
	add.x alltoall64.x barrier.x broadcast32.x broadcast64.x \
	collect32.x collect64.x cswap_eq.x cswap_neq.x \
	fadd.x fcollect32.x fcollect64.x fetch.x \
	finc.x get.x get_ipi.x get_nb.x get_nb_dual.x hello.x inc.x put.x \
	put32.x put64.x put_nb.x put_nb_dual.x reduce.x set.x \
	swap.x

OBJ_FILES = $(DEPENDS) $(SRC_FILES:.c=.o)

all: $(TARGETS)

info: all $(TARGETS)

.PHONY: clean install uninstall

.SUFFIXES:
.SUFFIXES: .c .o .x

ctimer.o: ctimer.c
	e-gcc -c $< -o $@

.c.o:
	coprcc -c $(DEFS) $(INCS) $(LIBS) $<

%.x: %.c $(DEPENDS)
	coprcc $(DEFS) $(INCS) $(LIBS) $< $(DEPENDS) -o $@

%.o: %.x
	coprcc --extract $< -o $@
	coprcc-info -j -l 100 $@

clean:
	rm -f *.o

distclean: clean 
	rm -f *.x
