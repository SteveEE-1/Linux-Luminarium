# Documentation Arguments

### Challenge

The typical need you'll have for documentation is just to figure out how to use all these dang programs, and a specific case of that is figuring out what arguments to specify on the command line. This module will mostly dig into that concept, as a proxy for figuring out how to use the programs in general. Through the rest of the module, you'll go through various ways of asking the environment for help for the programs, but first, we'll dig into the concept of reading documentation.

```bash
The correct usage of programs depends, in a large part, in the proper specification of arguments to them. Recall the -a of ls -a in the hidden files challenge of the Basic Commands module: that -a was an argument that told ls to list out hidden files as well as non-hidden files. Because we wanted to list out hidden files, invoking ls with the -a argument was the correct way to use it in our scenario.

```
The program for this challenge is /challenge/challenge, and you'll need to invoke it properly in order for it to give you the flag. Let's pretend that this is its documentation:

Welcome to the documentation for /challenge/challenge! To properly run this program, you will need to pass it the argument of --giveflag. Good luck!

Given that knowledge, go get the flag!



### Solve 

When you run /challenge/challenge --giveflag, the following happens:

1. The shell looks for the program /challenge/challenge.
2. If the file exists and has executable permissions, it runs.
3. The program checks its input arguments.
4. If --giveflag is provided, the program prints the flag.
5. If the argument is missing or incorrect, the program might print an error or a usage message.

hence after typing **/challenge/challenge --giveflag** we invoke the flag



### Flag
`pwn.college{8H009X_ghlxSJ_lVfvE_z027qR0.dRjM5QDLwkTN4kzW}`


##
# Complex Arguments 

### Challenge

While using most commands is straightforward, the usage of some commands can get quite complex. For example, the arguments to commands like sed and awk, which we're definitely not getting into right now, are entire programs in an esoteric programming language! Somewhere on the spectrum between cd and awk are commands that take arguments to their arguments...


This sounds crazy, but you've already encountered this with the find level in Basic Commands. find has a -name argument, and the -name argument itself takes an argument specifying the name to search for. Many other commands are analogous.

Here is this level's documentation for /challenge/challenge:

Welcome to the documentation for /challenge/challenge! This program allows you to print arbitrary files to the terminal, when given the --printfile argument. The argument to the --printfile argument is the path of the flag to read. For example, /challenge/challenge --printfile /challenge/DESCRIPTION.md will print out the description of the level!

Given that documentation, go get the flag!



### Solve

we just need to inculcate instead of /challenge/DESCRIPTION.md we can instead 
write flag which is a file containing the flag we need. hence this just invokes 
the file and returns the flag to us.





##

# Searching for Manuals

### Challenge

You can scroll man pages with the arrow keys (and PgUp/PgDn) and search with /. After searching, you can hit n to go to the next result and N to go to the previous result. Instead of /, you can use ? to search backwards!

Find the option that will give you the flag by reading the challenge man page.



### Solve

We just need to man the challenge. Which opens up the manual to a bunch of commands
through which we use the `/` to searches the manual to find which command might invoke what 
we need.



### Flag
`pwn.college{wnczuByYE2w2OPoKvD307cmGgh3.dZTM4QDLwkTN4kzW}`





