#Welcome to the C notes

###Makefiles
Makefiles are used to stitch the whole program together. The makefile is how all the libraries and your code are put together into one file for the compiler to process.

The general rule is 
> target: prereq1 prereq2
>
> \t  commands

for instance:
>count_words: count_words.o lexer.o
>
>\t gcc count_words.o lexer.o -lfl -o count_words
>
>count_words.o: count_words.c
>
>\t gcc -c count_words.c
>
>lexer.o: lexer.c
>
> \t gcc -c lexer.c
>
> lexer.c: lexer.l
>
>
> \t flex -t lexer.l > lexer.c

To make things easier, programmers introduced *phony targets*.
Phony targets are always out of date. This is an example of phony targets for the abover example

> all: count_words
>
> clean:
>
> \t rm -f count_words*.o lexer.c

###Standard phony targets:
+ **all** : Perform all tasks to build the app
+ **install**: Create an installation of the app form the compiled binaries
+ **clean**: Delete the binary files generated from sources
+ **distclean**: Delete all the generated files that were not in the original source distribution
+ **TAGS**: Create a tags table for use by editors
+ **check**: Run any tests associated with this application



