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


# Cat 

## cat a file

### Challenge


One of the most critical Linux commands is cat. cat is most often used for reading out files, like so:

hacker@dojo:~$ cat /challenge/DESCRIPTION.md
One of the most critical Linux commands is `cat`.
`cat` is most often used for reading out files, like so:

cat will concatenate (hence the name) multiple files if provided multiple arguments. For example:
```bash
hacker@dojo:~$ cat myfile
This is my file!
hacker@dojo:~$ cat yourfile
This is your file!
hacker@dojo:~$ cat myfile yourfile
This is my file!
This is your file!
hacker@dojo:~$ cat myfile yourfile myfile
This is my file!
This is your file!
This is my file!
```

Finally, if you give no arguments at all, cat will read from the terminal input and output it. We'll explore that in later challenges...

In this challenge, I will copy the flag to the flag file in your home directory (where your shell starts). Go read it with cat!

### Solve

Changing the director to ``/`` and then catting the flag file will invoke the flag. 

### flag 

`pwn.college{854TpKiLLVYslvWrHZK7i0FXthF.dFzN1QDL4czNOCZW}`



# Touch


## Creating a file

### Challenge


Of course, you can also create files! There are several ways to do this, but we'll look at a simple command here. You can create a new, blank file by touching it with the touch command:

```bash
hacker@dojo:~$ cd /tmp
hacker@dojo:/tmp$ ls
hacker@dojo:/tmp$ touch pwnfile
hacker@dojo:/tmp$ ls
pwnfile
hacker@dojo:/tmp$
```
It's that simple! In this level, please create two files: /tmp/pwn and /tmp/college, and run /challenge/run to get your flag!



### Solve 

Straight forward challenge as we just need to make two files using the touch command and then to 
`/challenge/run` to invoke the flag. Touch command just creates a files in specific directiories
if mentioned.


### Flag

`pwn.college{sxgoz1S6ca__b_TC1dDsDizXtMS.dBzM4QDL4czN0czW}`



# Removing 

## Removing files

### CHallenge


Files are all around you. Like candy wrappers, there'll eventually be too many of them. In this level, we'll learn to clean up!

In Linux, you remove files with the rm command, as so:
```bash
hacker@dojo:~$ touch PWN
hacker@dojo:~$ touch COLLEGE
hacker@dojo:~$ ls
COLLEGE     PWN
hacker@dojo:~$ rm PWN
hacker@dojo:~$ ls
COLLEGE
hacker@dojo:~$
```
Let's practice. This challenge will create a delete_me file in your home directory! Delete it, then run /challenge/check, which will make sure you've deleted it and then give you the flag!




### Solve

First we need to view which all directories are there in our cwd as then all the directories available will be shown. Then we simply just type `rm delete_file` (which is the file name in this case) and enter. after that we just type the `/challenge/check` checks if the files been deleted and if yes then it invokes the flag

### Flag

`pwn.college{MTlreXe5peZraeMLLo1ZaDXK-JE.dZTOwUDL4czN0czW}`



# Hidden Files  

## Challenge  

```
Interestingly, `ls` doesn't list all the files by default. Linux has a convention where files that start with a `.` don't show up by default in `ls` and in a few other contexts. To view them with `ls`, you need to invoke `ls` with the `-a` flag, as so:  
```


Now, it's your turn! Go find the flag, hidden as a dot-prepended file in `/`.  

```bash
hacker@dojo:$ touch pwn
hacker@dojo:$ touch .college
hacker@dojo:$ ls
pwn
hacker@dojo:$ ls -a
.college pwn
hacker@dojo:~$
```

Now, it's your turn! Go find the flag, hidden as a dot-prepended file in `/`.  

## Solve  

To locate the hidden flag file, follow these steps:  

1. Navigate to the root directory `/` if you are not already there:  
   ```bash  
   cd /  
   ```
2. Use the ls command with the -a flag to list all files, including hidden ones:  
   ```bash
   ls -a
   ```

3. Look for a file whose name starts with a dot (.), as hidden files follow this naming convention (e.g., .flag, .hidden_flag).

4. Once identified, use the cat command to read the contents of the hidden file and reveal the flag:

```bash 
cat .<filename>  
```
Replace **filename** with the actual name of the hidden file.


### Flag

`pwn.college{Ak7sVdqbh604_sG7U7bEhT1wTuu.dBTN4QDLwkTN4kzW}`



# An Epic FileSystem Quest

### Challenge

With your knowledge of cd, ls, and cat, we're ready to play a little game!

We'll start it out in /. Normally:

```bash
hacker@dojo:~$ cd /
hacker@dojo:/$ ls
bin   challenge  etc   home  lib32  libx32  mnt  proc  run   srv  tmp  var
boot  dev        flag  lib   lib64  media   opt  root  sbin  sys  usr
```

That's a lot of contents! One day, you will be quite familiar with them, but already, you might recognize the flag file and the challenge directory.

In this challenge, I have hidden the flag! Here, you will use ls and cat to follow my breadcrumbs and find it! Here's how it'll work:

Your first clue is in /. Head on over there.
Look around with ls. There'll be a file named HINT or CLUE or something along those lines!
cat that file to read the clue!
Depending on what the clue says, head on over to the next directory (or don't!).
Follow the clues to the flag!

Good luck!


## Solve    

1. First of we cd into the `/` and use the ls commands to display all the directories  and files in that directory. We come across a file named 

```bash
hacker@commands~an-epic-filesystem-quest:/$ ls
BLUEPRINT  bin	boot  challenge  dev  etc  flag  home  lib  lib32  lib64  libx32  media  mnt  nix  opt	proc  root  run  sbin  srv  sys  tmp  usr  var
```

2. **BLUEPRINT** is a matching our description for HINT and CLUE. So hence we can cat the file

```bash
hacker@commands~an-epic-filesystem-quest:/$ cat BLUEPRINT 
Lucky listing!
The next clue is in: /usr/share/doc/libumfpack5
```

3. Then we have to cd into `usr/share/doc/libumfpack5` and ls to find out which all files are there

```bash
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/libumfpack5$ ls
NEWS.Debian.gz	SNIPPET  changelog.Debian.gz  copyright
```

4. Here the SNIPPET file once we use the cat operation reveals the next clue

```bash
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/libumfpack5$ cat SNIPPET 
Great sleuthing!
The next clue is in: /opt/libslub

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
```

5. Now we cd into the directory mentioned and use the ls command

```bash
hacker@commands~an-epic-filesystem-quest:/usr/share/doc/libumfpack5$ cd /opt/libslub
hacker@commands~an-epic-filesystem-quest:/opt/libslub$ ls
INFO  LICENSE  README.md  docs	libslub  libslub.py  reload.sh	requirements.txt  test
```

6. here we **cat** the INFO to reveal the next clue 

```bash
Tubular find!
The next clue is in: /usr/lib/python3/dist-packages/sympy/multipledispatch/tests/__pycache__

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
```

7. We cant cd into the directory since the challenge will reset hence we cat the destination relatively via the path.


```bash
hacker@commands~an-epic-filesystem-quest:/opt/libslub$ cat /usr/lib/python3/dist-packages/sympy/multipledispatch/tests/__pycache__/CUE-TRAPPED 
Yahaha, you found me!
The next clue is in: /usr/share/javascript/mathjax/jax/output/SVG/fonts/Gyre-Termes/Size3
```

8. Now we cd into the directory mentioned

```bash
hacker@commands~an-epic-filesystem-quest:/opt/libslub$ cd /usr/share/javascript/mathjax/jax/output/SVG/fonts/Gyre-Termes/Size3
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/SVG/fonts/Gyre-Termes/Size3$ ls
POINTER  Regular

``` 
9. Cat the file **POINTER**

```bash
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/SVG/fonts/Gyre-Termes/Size3$ cat POINTER 
Great sleuthing!
The next clue is in: /opt/linux/linux-5.4/drivers/iio/temperature

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
```

10. Now we cd into the directory mentioned and use a spcial ls command which is `ls -a` inorder to reveal hidden files.

```bash
hacker@commands~an-epic-filesystem-quest:/usr/share/javascript/mathjax/jax/output/SVG/fonts/Gyre-Termes/Size3$ cd /opt/linux/linux-5.4/drivers/iio/temperature
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/iio/temperature$ ls -a
.  ..  .MEMO  Kconfig  Makefile  hid-sensor-temperature.c  max31856.c  maxim_thermocouple.c  mlx90614.c  mlx90632.c  tmp006.c  tmp007.c  tsys01.c  tsys02d.c
```

11. Then we can **cat** the **.MEMO** file and it reveals the next clue

```bash
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/iio/temperature$ cat .MEMO
Congratulations, you found the clue!
The next clue is in: /usr/local/lib/python3.8/dist-packages/future-1.0.0.dist-info

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
```
12. Now we cd into the directory mentioned 

```bash
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/iio/temperature$ cd /usr/local/lib/python3.8/dist-packages/future-1.0.0.dist-info
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/future-1.0.0.dist-info$ ls
DISPATCH  INSTALLER  LICENSE.txt  METADATA  RECORD  WHEEL  entry_points.txt  top_level.txt
```

13. Now we cat the file **DISPATCH** and it reveals the next clue

```bash
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/future-1.0.0.dist-info$ cat DISPATCH 
Congratulations, you found the clue!
The next clue is in: /usr/local/lib/python3.8/dist-packages/selenium/webdriver/remote/__pycache__

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
```

14. Now again we do the same step as **step 7**.

```bash
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/future-1.0.0.dist-info$ cat /usr/local/lib/python3.8/dist-packages/selenium/webdriver/remote/__pycache__/NUGGET-TRAPPED 
Tubular find!
The next clue is in: /usr/share/racket/pkgs/racket-doc/ffi

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
```

15. we cd into the directory and do the same process as **step 10**

```bash
hacker@commands~an-epic-filesystem-quest:/usr/local/lib/python3.8/dist-packages/future-1.0.0.dist-info$ cd /usr/share/racket/pkgs/racket-doc/ffi
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/racket-doc/ffi$ ls -a
.  ..  .SECRET	examples
```

16. Then we cat the file **.SECRET** and we invoke the flag

```bash
hacker@commands~an-epic-filesystem-quest:/usr/share/racket/pkgs/racket-doc/ffi$ cat .SECRET 
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{8zmLoPlnNbXd76oFEVLuM2oGD1k.dljM4QDLwkTN4kzW}
```
### Flag 

`pwn.college{8zmLoPlnNbXd76oFEVLuM2oGD1k.dljM4QDLwkTN4kzW}`



# Finding files


## Challenge

So now we know how to list, read, and create files. But how do we find them? We use the find command!

The find command takes optional arguments describing the search criteria and the search location. If you don't specify a search criteria, find matches every file. If you don't specify a search location, find uses the current working directory (.). For example:

```bash
hacker@dojo:~$ mkdir my_directory
hacker@dojo:~$ mkdir my_directory/my_subdirectory
hacker@dojo:~$ touch my_directory/my_file
hacker@dojo:~$ touch my_directory/my_subdirectory/my_subfile
hacker@dojo:~$ find
.
./my_directory
./my_directory/my_subdirectory
./my_directory/my_subdirectory/my_subfile
./my_directory/my_file
hacker@dojo:~$
```

And when specifying the search location:

```bash
hacker@dojo:~$ find my_directory/my_subdirectory
my_directory/my_subdirectory
my_directory/my_subdirectory/my_subfile
hacker@dojo:~$
```

And, of course, we can specify the criteria! For example, here, we filter by name:

```bash
hacker@dojo:~$ find -name my_subfile
./my_directory/my_subdirectory/my_subfile
hacker@dojo:~$ find -name my_subdirectory
./my_directory/my_subdirectory
hacker@dojo:~$
```

You can search the whole filesystem if you want!

```bash
hacker@dojo:~$ find / -name hacker
/home/hacker
hacker@dojo:~$
```
Now it's your turn. I've hidden the flag in a random directory on the filesystem. It's still called flag. Go find it!

Several notes. First, there are other files named flag on the filesystem. Don't panic if the first one you try doesn't have the actual flag in it. Second, there're plenty of places in the filesystem that are not accessible to a normal user. These will cause find to generate errors, but you can ignore those; we won't hide the flag there! Finally, find can take a while; be patient!




### Solve 

We can use the command straight away by mentioning a specific file name to search the entire filesystem. They have given as the example in the question itself. So to imply to search for a particular file or directory. So the format is `find <directory_to_be_searched> <options> <filters>`

**EXAMPLE**

```bash
find <directory_to_be_searched> -type f -name "example.txt"

find <directory_to_be_searched> -type f -name "*.log"

find <directory_to_be_searched> -type f -size +10M
```
For this current scenario we just can directly search the entire filesystem. hence we come across many directory paths which contain the file flag. Its just a trial and error to find which one it is and using the cat command to invoke the flag 

```bash
cat /usr/share/racket/pkgs/plot-lib/plot/typed/flag
pwn.college{IBF8sj66RGqRFrDn8F8k0_lFoyW.dJzM4QDLwkTN4kzW}
```


### Flag

`pwn.college{IBF8sj66RGqRFrDn8F8k0_lFoyW.dJzM4QDLwkTN4kzW}`



# Linking files



### Challenge 

If you use Linux (or computers) for any reasonable length of time to do any real work, you will eventually run into some variant of the following situation: you want two programs to access the same data, but the programs expect that data to be in two different locations. Luckily, Linux provides a solution to this quandry: links.

Links come in two flavors: hard and soft (also known as symbolic) links. We'll differentiate the two with an analogy:

    A hard link is when you address your appartment using multiple addresses that all lead directly to the same place (e.g., Apt 2 vs Unit 2).
    A soft link is when you move appartments and have the postal service automatically forward your mail from your old place to your new place.

In a filesystem, a file is, conceptually, an address at which the contents of that file live. A hard link is an alternate address that indexes that data --- accesses to the hard link and accesses to the original file are completely identical, in that they immediate yield the necessary data. A soft/symbolic link, instead, contains the original file name. When you access the symbolic link, Linux will realize that it is a symbolic link, read the original file name, and then (typically) automatically access that file. In most cases, both situations result in accessing the original data, but the mechanisms are different.

Hard links sound simpler to most people (case in point, I explained it in one sentence above, versus two for soft links), but they have various downsides and implementation gotchas that make soft/symbolic links, by far, the more popular alternative.

In this challenge, we will learn about symbolic links (also also known as symlinks). Symbolic links are created with the ln command with the -s argument, like so:

```bash
hacker@dojo:~$ cat /tmp/myfile
This is my file!
hacker@dojo:~$ ln -s /tmp/myfile /home/hacker/ourfile
hacker@dojo:~$ cat ~/ourfile
This is my file!
hacker@dojo:~$
```

You can see that accessing the symlink results in getting the original file contents! Also, you can see the usage of **ln -s**. Note that the original file path comes before the link path in the command!

A symlink can be identified as such with a few methods. For example, the file command, which takes a filename and tells you what type of file it is, will recognize symlinks:


```bash
hacker@dojo:~$ file /tmp/myfile
/tmp/myfile: ASCII text
hacker@dojo:~$ file ~/ourfile
/home/hacker/ourfile: symbolic link to /tmp/myfile
hacker@dojo:~$
```

Okay, now you try it! In this level the flag is, as always, in **/flag**, but **/challenge/catflag** will instead read out **/home/hacker/not-the-flag**. Use the symlink, and fool it into giving you the flag!

### Solve 

1. We first create a link. the format to create a link is:

```bash
ln -s <target_file> <link_name>
```
So we have to link the **/flag** to the path they have given us which is **/home/hacker/not-the-flag** 

```bash
hacker@commands~linking-files:/challenge$ ln -s /flag /home/hacker/not-the-flag
```

After this it's mentioned in the question that the **link_name** provided to us reads from **/home/hacker/not-the-flag** so hence we can just call the command `/challenge/catflag` to invoke the flag

### Flag

`pwn.college{Erh2CsxT0YEu7B0BQBFZKsbSjyK.dlTM1UDLwkTN4kzW}`



