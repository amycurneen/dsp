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

* pwd (show current working directory path)
* mkdir Hello (creating a directory)
* rm -r Hello (deleting a directory)
* touch Hello.txt (creating a file using `touch` command)
* rm Hello.txt (deleting a file)
* mv Hello.txt Hello_new.txt (renaming a file)
* ls -a (listing hidden files)
* cp Hello.txt New_Hello (copying a file from one directory to another)
* cat Hello.txt (outputs the contents of file to terminal)
* cat Hello_English.txt >> Hello_Languages.txt (Appends output to a file)

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

`ls` (Lists files and folders in working directory)

`ls -a` (Lists files and folders in working directory including hidden ones starting with a dot) 

`ls -l` (Lists files and folders in working directory in long format - Table output) 

`ls -lh` (Lists files and folders in working directory in long format - Table output with print sizes in human readable format) 

`ls -lah` (Lists files and folders in working directory in long format - Table output with print sizes in human readable format including hidden files and folders starting with a dot)

`ls -t` (Lists files and folders in working directory, ordered by modified date) 

`ls -Glp` (Lists files and folders in working directory in long format - Table output with a slash after each directory, not displaying group)

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

`ls -R` (Lists files and folders in working directory and subdirectories)

`ls -q` (Lists files and folders in working directory with non-printing characters as a ?)

`ls -1` (Lists files and folders in working directory with each entry on one line)

`ls -d` (Lists only directories in working directory)

`ls -c` (Lists files and folders in working directory by file timestamp)

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

`xargs` is a command in Unix which builds and executes command lines from a standard input.

Ex:

`echo 'Hello1 Hello2 Hello3' | xargs mkdir`

`ls`

`Hello1 Hello2 Hello3`

`xargs` allows mkdir to use a standard input to create directories
