The source code of this package compiles a program called mini, a type
inference engine for the Mini language.

# How to compile the source code ?

Decompress the distributed package. In the newly created folder, do:

    # ./configure

This should check if you have the necessary tools to compile [mini].
Then, you just have to launch the compilation using:

    # make

To generate this documentation, type the following command:

    # make doc

Do not hesitate to contact yann.regis-gianas@inria.fr if the compilation
process fails.

# Usage

A basic usage of mini is to provide a source file as input. Let's
foo.ml be this file:

    let id x = x

Running

    # mini foo.ml

returns

    val id: forall a. a -> a

The documentation of the module MiniAst explains the concrete syntax
of the Mini language. The "tests" directory contains examples of
valid Mini programs.

# Options

By default, `mini` processes the following tasks:

- parse-program, parse the input file as a Mini program
- generate-constraint, generate the typing constraint of this program
- solve-constraint, solve this constraint
- print-env, print the types of the toplevel definitions


These tasks are optional:

-  print-program, pretty-print the parsed program
-  parse-constraint, parse the input file as a typing constraint not as
   a Mini program
-  print-constraint, print the typing constraint

The options of `mini` enable the use of these optional tasks:

    usage: ./mini [options] filename
      --start taskname             Task to begin with
      --end taskname               Task to end with
      --trace-all                  Trace
      --do taskname                Do a task
      --trace-solve-constraint     Trace solve-constraint
      --trace-print-program        Trace print-program
      --trace-generate-constraint  Trace generate-constraint
      --trace-print-constraint     Trace print-constraint
      --trace-parse-program        Trace parse-program
      --trace-print-env            Trace print-env
      --trace-parse-constraint     Trace parse-constraint
      -help                        Display this list of options
      --help                       Display this list of options

