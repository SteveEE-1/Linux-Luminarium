# Matching with *


## Challenge 

The first glob we'll learn is *. When it encounters a * character in any argument, the shell will treat it as "wildcard" and try to replace that argument with any files that match the pattern. It's easier to show you than explain:

```bash
hacker@dojo:~$ touch file_a
hacker@dojo:~$ touch file_b
hacker@dojo:~$ touch file_c
hacker@dojo:~$ ls
file_a	file_b	file_c
hacker@dojo:~$ echo Look: file_*
Look: file_a file_b file_c
```


Of course, though in this case, the glob resulted in multiple arguments, it can just as simply match only one. For example:

```bash 
hacker@dojo:~$ touch file_a
hacker@dojo:~$ ls
file_a
hacker@dojo:~$ echo Look: file_*
Look: file_a
```

When zero files are matched, by default, the shell leaves the glob unchanged:

```bash
hacker@dojo:~$ touch file_a
hacker@dojo:~$ ls
file_a
hacker@dojo:~$ echo Look: nope_*
Look: nope_*
```

The * matches any part of the filename except for / or a leading . character. For example:


```bash
hacker@dojo:~$ echo ONE: /ho*/*ck*
ONE: /home/hacker
hacker@dojo:~$ echo TWO: /*/hacker
TWO: /home/hacker
hacker@dojo:~$ echo THREE: ../*
THREE: ../hacker
```

Now, practice this yourself! Starting from your home directory, change your directory to /challenge, but use globbing to keep the argument you pass to cd to at most four characters! Once you're there, run /challenge/run for the flag!



### Solve


We just basically instead of writing the directory to change to we simply use the * match the **directory** name to change to or **filename**.So here we type `cd /ch*` which is `cd /challenge` to change to directory and `/challenge/run` to invoke the flag.


### Flag 
`pwn.college{oiKLxxMyq-cLPpqqGDNe9kOzH6X.dFjM4QDLwkTN4kzW}`



# Matching with ? 


Next, let's learn about ?. When it encounters a ? character in any argument, the shell will treat it as single-character wildcard. This works like *, but only matches one character. For example:

```bash
hacker@dojo:~$ touch file_a
hacker@dojo:~$ touch file_b
hacker@dojo:~$ touch file_cc
hacker@dojo:~$ ls
file_a	file_b	file_cc
hacker@dojo:~$ echo Look: file_?
Look: file_a file_b
hacker@dojo:~$ echo Look: file_??
Look: file_cc
```

Now, practice this yourself! Starting from your home directory, change your directory to /challenge, but use the ? character instead of c and l in the argument to cd! Once you're there, run /challenge/run for the flag!



### Solve

This command is used to search or cd into  directory or file by putting `?` which treats it as a single characted wild card. which then we use it like this `cd /?ha??enge` (since we werent allowed to use the letters C and L).
we then invoke the flag by running **/challenge/run**


### Flag 

`pwn.college{weobYfIBu6HMXTmNAKqMwqJR5Wm.dJjM4QDLwkTN4kzW}`


