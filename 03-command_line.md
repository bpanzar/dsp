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

>> pwd : show current working directory path
>> mkdir : create a directory
>> rm -r : delete a directory and all of its child directories
>> touch filename : create a file
>> rm : delete a file
>> mv filename newfilename : rename a file
>> ls -a : list hidden files
>> cp filename destination : copy a file from one director to the other
>> cat : outputs the contents of a file to the terminal
>> | : pipes the output of one command to the input of another command

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

> > ls : lists the files in the current directory
    ls -a : list files including hidden files
    ls -l : lists all contents of a directory in long format
    ls -lh : lists contents in long format but uses unit suffixes for file size
    ls -lah : same as '-lh' however includes hidden entries
    ls -t: sort by most recently modified time
    ls -Glp: enable colorized output and write a '/' after each directory name

---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

> > -d : displays only directories
    -r : displays files in reverse order
    -u : displays files by the file access time
    -F : flags filenames
    -m : displays the names as a comma-separated list

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

> > Researching this.

 

