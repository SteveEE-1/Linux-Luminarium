# GREP

## I like greps :D

### Challenge

Sometimes, the files that you might cat out are too big. Luckily, we have the grep command to search for the contents we need! We'll learn it in this challenge.

There are many ways to grep, and we'll learn on way here:
```
hacker@dojo:~$ grep SEARCH_STRING /path/to/file
```
Invoked like this, grep will search the file for lines of text containing SEARCH_STRING and print them to the console.

In this challenge, I've put a hundred thousand lines of text into the /challenge/data.txt file. Grep it for the flag!

HINT: The flag always starts with the text pwn.college.


### Solve

grep command allows us to find a string in a file containing many characters. It an efficient tool. First we need to change the directory to `/` and after that use the grep command to find the particular string in directory `challenge/data.txt` which then invokes the flag.

### Flag

`pwn.college{ciiMs5cmnIBuGbghHbI1E0FxVxa.ddTM4QDLwkTN4kzW}`


# Listing

## listing files

### Challenge


So far, we've told you which files to interact with. But directories can have lots of files (and other directories) inside them, and we won't always be here to tell you their names. You'll need to learn to list their contents using the ls command!

ls will list files in all the directories provided to it as arguments, and in the current directory if no arguments are provided. Observe:
```
hacker@dojo:~$ ls /challenge
run
hacker@dojo:~$ ls
Desktop    Downloads  Pictures  Templates
Documents  Music      Public    Videos
hacker@dojo:~$ ls /home/hacker
Desktop    Downloads  Pictures  Templates
Documents  Music      Public    Videos
hacker@dojo:~$
```

In this challenge, we've named /challenge/run with some random name! List the files in /challenge to find it.


### Solve

Firstly we need to change the directory to the `/` and then ls which will display all the directories from them we change it to challenge where the run file is renmaed to a random name. When i tried catting it told i could `cat /flag` which then i was prompted with **permission denied** and then i just had to ls the cwd along with the newly named run file which was in this case `21699-renamed-run-30730` and it invoked the flag


### Flag

`pwn.college{wSlxC_tC9LcVqbpsGTytpCKXBfr.dhjM4QDLwkTN4kzW}`









# Touching (Cant believe even files can get harassed)

### Challenge

```

Of course, you can also create files! There are several ways to do this, but we'll look at a simple command here. You can create a new, blank file by touching it with the touch command:

hacker@dojo:~$ cd /tmp
hacker@dojo:/tmp$ ls
hacker@dojo:/tmp$ touch pwnfile
hacker@dojo:/tmp$ ls
pwnfile
hacker@dojo:/tmp$

It's that simple! In this level, please create two files: /tmp/pwn and /tmp/college, and run /challenge/run to get your flag!

```


### Solve


