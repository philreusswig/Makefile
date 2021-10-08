# rule: pre-requisite-1 pre-requisite-2 ...
#	 command

all: hello.exe									# default target

hello.exe: hello.o
	gcc -o hello.exe hello.o

hello.o: hello.c
	gcc -c hello.c

clean:											# optional target
	rm hello.o hello.exe