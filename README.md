# nshc - new shell compiler

## shc

A Bash scripting language compiler that really compiles...

This is inspired/forked from Jahidul Hamid and intika's update ([v.4.03](https://github.com/neurobin/shc)) of Francisco Javier Rosales García's version ([v.3.89](https://www.datsi.fi.upm.es/~frosal)) of shc, the "generic shell script compiler."  The shc (v.4.03) source code can be found under the [v1](v1) directory.  

shc, however, doesn't actually compile shell scripts into machine language/binary executables per se. It encrypts the script and embeds them in a C wrapper which is then compiled into a binary executable.  This binary, when executed, decrypts the shell script and executes it in the shell which the script shebang invokes.  These binaries, then, are still dependent upon the shell for which the script was written.  shc also implements some interesting features, such as binary expiration (see their documentation for more information on this).

shc's "main purpose", according to its man page, "is to protect your shell scripts from modification or inspection. You can use it if you wish to distribute your scripts but don't want them to be easily readable by other people."  It is, therefore, a method of script obscuration rather than a transpiler/compiler of the Bash scripting language. 

## nshc - IN PROGRESS

nshc, on the other hand, is an llvm frontend for the Bash scripting language, targeting Bash version 4.0, which implemented associative arrays. 

The Bash shell is written in C. nsch follows suit and implements the Bash scripting language in C, inlining Bash "builtins" as needed.  Non-builtin commands are invoked using forked exec() functions.  This C code will be transpiled into llvm IR (intermediate representation), allowing Bash shell scripts to be compiled into native binary executables.  

Such binaries should be dynamic and stripped to reduce their size as much as possible, but that's a backend compiler decision and isn't determined by nshc.


## Resources
[Scripting reference](https://decal.ocf.berkeley.edu/labs/scripting/)


