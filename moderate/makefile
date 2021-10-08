CC=gcc
CFLAGS=-g -Wall

SRC=src
OBJ=obj
SRCS=$(wildcard $(SRC)/*.c)
OBJS=$(patsubst $(SRC)/%.c, $(OBJ)/%.o, $(SRCS))
HDRS=$(wildcard $(SRC)/*.h)

BINDIR=bin
BIN=$(BINDIR)/main
SUBMITNAME=project.zip

all: $(BIN)

release: CFLAGS=-Wall -02 -DNDEBUG
release: clean
release: $(BIN)

$(BIN): $(OBJS) $(OBJ) 
	$(CC) $(CFLAGS) $(OBJS) -o $@  $(LDFLAGS)

$(OBJ)/%.o: $(SRC)/%.c $(OBJ)
	$(CC) $(CFLAGS) -c $< -o $@ 

$(OBJ): 
	mkdir -p $@

clean:
	$(RM) -r $(BINDIR)/* $(OBJ)/*

submit:
	$(RM) $(SUBMITNAME)
	zip $(SUBMITNAME) $(BIN)