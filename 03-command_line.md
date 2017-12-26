# Learn command line

Please follow and complete the free online [Bash Scripting Tutorial](https://ryanstutorials.net/bash-scripting-tutorial/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. You should be able to go through these in a couple of hours.

**Note:** Bash is not installed on a PC. Rather, PC users must install Cygwin. Once Cygwin has been installed, the command line interface witll _emulate_ bash. You can find all information regarding Cygwin [here](https://www.cygwin.com/).

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

`pwd` - show current working directory path
`mkdir` - creating a directory
`rm -r` - deleting a directory (and sub-directories)
`touch` - creating a file using `touch` command
`rm` - deleting a file
`mv` - renaming a file (also used to move files from one directory to another)
`ls -a` -listing hidden files
`cp` - copying a file from one directory to another
`>>`  - add contents of one file to another
`sort` - sort the contents of a file

---

### Q2.  List Files in Unix   

What do the following commands do:  
`ls` 
`ls -a`  
`ls -l`  
`ls -lh`  
`ls -lah`  
`ls -t`  
`ls -Glp`  

`ls` - list files in a directory
`ls -a` - list files in a directory including hidden files 
`ls -l` - list contents of a file in long format
`ls -lh` - list long format with  readable filesize 
`ls -lah` - list long format with readable filesize including hidden files
`ls -t` - order files and directories by time of last modification
`ls -Glp` - list contents of file in long format, with `/` seperator

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

`ls -S` - order files by filesize
`ls -R` - recursively list files and directories
`ls -x` - list files in row format
`ls -s` - indicate filesize in blocks
`ls -u` - list files by last access time

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

`xargs` lets /bin commands such as `echo` and `mkdir` access standard input as arguments. For example, we can use xargs to create directories using a string:

`$ echo "one, two, three" | xargs mkdir`

 

