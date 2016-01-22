# The LEMON Parser Generator

The Lemon program is an LALR(1) parser generator. It takes a context free
grammar and converts it into a subroutine that will parse a file using that
grammar.

Lemon is similar to the much more famous programs "YACC" and "BISON". But lemon
is not compatible with either yacc or bison. There are several important
differences:

* Lemon using a different grammar syntax which is less prone to programming
errors.
* The parser generated by Lemon is both re-entrant and thread-safe.
* Lemon includes the concept of a non-terminal destructor, which makes it much
easier to write a parser that does not leak memory.

The complete source code to the lemon parser generator is contained in two
files. The file
[lemon.c](https://github.com/compiler-dept/lemon/blob/master/lemon.c) is the
parser generator program itself. A separate file
[lempar.c](https://github.com/compiler-dept/lemon/blob/master/lemon.c) is the
template for the parser subroutine that lemon generates.
[Documentation](http://www.hwaci.com/sw/lemon/lemon.html) on lemon is also
available.

Both the source code to lemon itself and the code that lemon generates are in
the public domain.

To see an example of how to use lemon, see the source code to the SQLite
database engine. Lemon is maintained as part of the
[SQLite](http://www.sqlite.org/) project.

# Use

Lemon is intended to be used as a self contained part of your project. We set
this repository up to make it possible to use Lemon through a git submodule.
This helps you, to easily update your Lemon dependency. We keep track of new
releases.

To set up your Lemon through a git submodule run the following line in your
projects root folder:

    git submodule add https://github.com/compiler-dept/lemon.git lemon

As Lemon needs to be compiled, you can easily add lemon to your Makefile:

    lemon:
        @make -C lemon
