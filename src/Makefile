CC=gcc
CFLAGS=-I$(IDIR) 
LDFLAGS=-lm

IDIR=../include
ODIR=obj

_DEPS = utilities.h bitboard.h pawn.h mvgen.h state.h evaluate.h search.h mt64.h
DEPS = $(patsubst %,$(IDIR)/%,$(_DEPS))
 
_OBJ = main.o utilities.o bitboard.o pawn.o mvgen.o state.o evaluate.o search.o mt19937-64.o opening.o
OBJ = $(patsubst %,$(ODIR)/%,$(_OBJ))

$(ODIR)/%.o: %.c $(DEPS)
	$(CC) -c -o $@ $< $(CFLAGS) $(LDFLAGS)

viper: $(OBJ)
	$(CC) -o $@ $^ $(CFLAGS) $(LDFLAGS)
	rm obj/*

.PHONY: clean

clean:
	rm -f $(ODIR)/*.o *~ core $(IDIR)/*~