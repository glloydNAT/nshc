# nshc - new shell compiler

A Bash compiler that really compiles...

This is a forked from Jahidul Hamid and intika's update ([v.4.03](https://github.com/neurobin/shc)) of Francisco Javier Rosales García's version ([v.3.89](https://www.datsi.fi.upm.es/~frosal)) of shc, the "generic shell script compiler."

shc, however, doesn't actually compile shell scripts into machine language/binary executables per se. It encrypts the script and embeds them in a C wrapper which is then compiled into a binary executable.  This binary, when executed, decrypts the shell script and executes it in the shell which the script shebang invokes.  These binaries, then, are still dependent upon the shell for which the script was written.  shc also implements some interesting features, such as binary expiration (see their documentation for more information on this).

shc's "main purpose", according to its man page, "is to protect your shell scripts from modification or inspection. You can use it if you wish to distribute your scripts but don't want them to be easily readable by other people."  It is, therefore, a method of script obscuration rather than a transpiler/compiler of the Bash scripting language. 




