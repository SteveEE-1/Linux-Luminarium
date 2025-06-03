# Pondering Path

## Implicit Relative Path 

### Challenge


Now you're familiar with the concept of referring to absolute paths and changing directories. If you put in absolute paths everywhere, then it really doesn't matter what directory you are in, as you likely found out in the previous three challenges.

However, the current working directory does matter for relative paths.

    A relative path is any path that does not start at root (i.e., it does not start with /).
    A relative path is interpreted relative to your current working directory (cwd).
    Your cwd is the directory that your prompt is currently located at.

This means how you specify a particular file, depends on where the terminal prompt is located.

Imagine we want to access some file located at /tmp/a/b/my_file.

    If my cwd is /, then a relative path to the file is tmp/a/b/my_file.
    If my cwd is /tmp, then a relative path to the file is a/b/my_file.
    If my cwd is /tmp/a/b/c, then a relative path to the file is ../my_file. The .. refers to the parent directory.

Let's try it here! You'll need to run /challenge/run using a relative path while having a current working directory of /. For this level, I'll give you a hint. Your relative path starts with the letter c 😊

### Solving

A relative path specifies the location of a file or directory relative to your current working directory (cwd). It does not start with / (the root directory) and changes depending on where you are in the filesystem.

To solve this challenge:
Start by changing your current working directory to ``/`` using the `` cd /`` command.From ``/``, the challenge folder is directly accessible as a relative path. The **run** file is located within the challenge folder.To execute the run file, use the relative path ``challenge/run``.

By running challenge/run from the / directory, you successfully invoke the program and retrieve the flag.

### Flag 
`pwn.college{II5NuCIjCGLtTPKarDArsiyu2SU.dlDN1QDLwkTN4kzW}`



# Explicit Relative Path 

### Challenge



Previously, your relative path was "naked": it directly specified the directory to descend into from the current directory. In this level, we're going to explore more explicit relative paths.

In most operating systems, including Linux, every directory has two implicit entries that you can reference in paths: . and ... The first, ., refers right to the same directory, so the following absolute paths are all identical to each other:
```
    /challenge
    /challenge/.
    /challenge/./././././././././
    /./././challenge/././
```
The following relative paths are also all identical to each other:
```
    challenge
    ./challenge
    ./././challenge
    challenge/.
```
Of course, if your current working directory is /, the above relative paths are equivalent to the above absolute paths.

This challenge will get you using . in your relative paths. Get ready!



## Solve

To access the particular directory we just need to use `./` which jumps up once closer to the parent directory to which in this case so we just jump back and then we invoke the command `./challenge/run`


### Flag

`pwn.college{kaxwKsme5chkC5oUyhxiPd38TCN.dBTN1QDLwkTN4kzW}`