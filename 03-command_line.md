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

`pwd` - show current working directory path<br/>
`mkdir` - creating a directory<br/>
`rm -r` - deleting a directory (and sub-directories)<br/>
`touch` - creating a file using `touch` command<br/>
`rm` - deleting a file<br/>
`mv` - renaming a file (also used to move files from one directory to another)<br/>
`ls -a` -listing hidden files<br/>
`cp` - copying a file from one directory to another<br/>
`>>`  - add contents of one file to another<br/>
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

`ls` - list files in a directory<br/>
`ls -a` - list files in a directory including hidden files <br/>
`ls -l` - list contents of a file in long format<br/>
`ls -lh` - list long format with  readable filesize<br/>
`ls -lah` - list long format with readable filesize including hidden files<br/>
`ls -t` - order files and directories by time of last modification<br/>
`ls -Glp` - list contents of file in long format, with `/` seperator<br/>

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

`ls -S` - order files by filesize<br/>
`ls -R` - recursively list files and directories<br/>
`ls -x` - list files in row format<br/>
`ls -s` - indicate filesize in blocks<br/>
`ls -u` - list files by last access time<br/>

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

`xargs` lets /bin commands such as `echo` and `mkdir` access standard input as arguments. For example, we can use xargs to create directories using a string:

`$ echo "one, two, three" | xargs mkdir`

 

