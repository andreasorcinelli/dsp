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

> >
#### A1.   Cheat Sheet of Commands
 
* **pwd**  show current working directory path
* **mkdir [directory]** create a directory
* **rmdir [directory]** delete a directory
* **touch [filename]** create a file using touch command
* **rm [file]** delete a file
* **mv [old file name][new file name]** rename a file
* **ls -a** list hidden files
* **cp [source] [destination]** copy a file from one directory to another
* **:q!** discard all changes, since the last save, and exit in VI text editor
* **:w** save file but don't exit in VI text editor
* **:wq**  save and exit in VI text editor
* **git status** show the working tree status
* **git add [filename]** add file contents to the index
* **git commit -m ['message']** record changes to the repo with a commit message
* **git push** update remote refs along with associated objects
* **git clone** clone a repo into a new directory
* **cd -** go to home directory
* **cd / -** go to the root directory
* **cd ..** go to parent directory
* **man [command]** look up the manual page for a particular command
* **clear** clear the terminal screen

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

> >
#### A2.   List Files in Unix

* **ls** list the contents of a directory
* **ls -a** list the contents of a directory including hidden files
* **ls -l** list the contents of a directory in long format
* **ls -lh** list the contents of a directory in long format with unit suffixes to reduce number of digits
* **ls -lah** list directory contents and include entires whose names begin with a dot 
* **ls -t** list directory contents and sort by time modified (most recently modified first) before sorting the operands by lexicographical order.
* **ls -Glp** list directory contents and enable colorized output, list in long format, write a slash after each file name if that file is a directoryE

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

> > 
#### A3. More List Files in Unix

* **ls -1** displays each entry on a line
* **ls -p** displays directories with /
* **ls -c** displays files by time stamp
* **ls -t** displays newest files first based on timestamp 
* **ls -d** displays only directories

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

> > 
#### A4.   Xargs

According to its manual page, the xargs command,  "constructs argument list(s) and execute utility” In other words, the xargs command is used to build an execution pipeline from standard input. Xargs is often used with the find command, for example, to search for files or directories and then operate on the results. If I wanted to find and delete all files that were last modified before a certain date, I could use xargs and rm to do this.

 

