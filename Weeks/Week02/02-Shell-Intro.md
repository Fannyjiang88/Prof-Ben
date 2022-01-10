# Introductory Bash demo

* This demo was inspired by Melanie Walsh's [Intro to the Command Line](https://melaniewalsh.github.io/Intro-Cultural-Analytics/01-Command-Line/01-The-Command-Line.html) (similar to this one)
* The commands shown are for Linux/Mac
* See the above intro and Melanie Walsh's Cheatsheet below for Windows-specific commands

---

## DEMO: Grabbing text from the web and analyzing it

1. Open a Terminal window
1. `pwd`: print working directory to see where we are
1. `ls`: list contents of the current directory
1. `mkdir <FOLDERNAME>`: make a directory named FOLDERNAME to hold our files
1. `cd <FOLDERNAME>`: change directory so that our current working directory is FOLDERNAME
    * This uses **relative path**, a pathname that is relative to the current directory
    * One can also specify an **absolute path**, a pathname that is relative to the root directory on the system
    * For example, if `pwd` gives `/home/jovyan`, then `cd folder01` uses relative path and `cd /home/jovyan/folder01` uses absolute path to navigate into the folder `/home/jovyan/folder01`
1. `ls`: review the current file list to check that nothing is there
1. `curl -O https://www.gutenberg.org/files/1533/1533-0.txt`: uses the `curl` command to grab a text file off the web at this URL
1. `ls`: list the files to check that it's been downloaded
    * `ls` can also be used with *flags*
	* `ls -a` includes hidden files (those starting with `.`
	* `ls -l` lists more verbose information about files
1. `mv 1533-0.txt macbeth.txt`: moves a file from one name to another name, i.e., this renames the file
1. write the file contents to standard output (here the terminal) to check that it's what we expect
    * `cat macbeth.txt`: write all file contents
    * `head macbeth.txt`: write the first lines
	* `tail macbeth.txt`: write the last lines
1. `wc macbeth.txt`: displays word count, line count, and byte count of the file
    * `wc -w macbeth.txt`: get word count 
	* `wc -l macbeth.txt`: get line count
1. `grep <STRING> macbeth.txt`: find matches of the STRING in the file
    * `-n`: include line numbers
	* `--color`: see colored match
	* `-wc`: show line counts of matches
	* `-B NUM1 -A NUM2`: show NUM1 lines before and NUM2 lines after the match
	
---

## Command Line Cheatsheet from Melanie Walsh's Introduction

| Mac / Chrome / Linux                            | Explanation                                                                                               | Windows PowerShell                                                                   |
|--------------------------------------------|-----------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------|
| `cd` *filepath*                            | **c**hange **d**irectory, aka move into a different folder                                                | `cd` *filepath*                                                                      |
| `ls`                                       | **l**i**s**t the files and folders in your current **dir**ectory                                          | `ls` / `dir` / `Get-ChildItem`                                                       |
| `pwd`                                      | show **p**ath of **w**orking **d**irectory, aka the folder that you're in right now                       | `pwd` / `cd`                                                                         |
| `touch` *filename*                         | make a new file                                                                                           | `ni` *filename*                                                                      |
| `mkdir` *directory-name*                   | **m**a**k**e a new **dir**ectory, aka a folder                                                            | `mkdir` *directory-name*                                                             |
| `rm` *filename*                            | **r**e**m**ove, aka delete, a file or directory                                                           | `rm` *filename* / `del` *filename*                                                   |
| `cp` *original-filename* *copied-filename* | **c**o**p**y a file or directory                                                                          | `cp` / `copy`                                                                        |
| `mv` *original-filename* *new-filename*    | **m**o**v**e or rename a file or directory                                                                | `move` *original-filename* *new-filename* / `ren` *original-filename* *new-filename* |
| `cat` *filename*                           | show all the contents of a file                                                                           | `cat` *filename* / `type` *filename*                                                 |
| `less` *filename*                          | show snippet of a file that allows you to scroll through the entire thing                                 | `more` *filename*                                                                    |
| `head` *filename*                          | show the first 10 lines of a file (change number of lines by adding `-*a number*` flag, e.g. `head -100`) | `gc` *filename* `-head 10`                                                           |
| `tail` *filename*                          | show the last 10 lines of a file (change number of lines by adding `-*a number*` flag, e.g. `tail -100`)  | `gc` *filename* `-tail 10`                                                           |
| `wc -w -l` *filename*                      | show how many **w**ords or lines in a file                                                                | `gc` *filename* \| `Measure-Object -Word –Line`                                      |
| `man` *command*                            | show the **man**ual, aka the documentation that tells you what a particular command does                  | `help` *command*                                                                               |
| `echo`                                     | print text to the command line                                                                            | `echo`                                                                               |
| `grep` "search term" *filename* or *directory-name*       |      search for lines that include search term in file                                                                                                     | `findstr` "search term" *filename*                                                                 |
| `curl -O` *url*            | **get**, a file from the **w**eb                                                                          | `wget` *url* `-OutFile` *new-filename*                                               |

---

## Resources:

* Melanie Walsh's [Intro to the Command Line](https://melaniewalsh.github.io/Intro-Cultural-Analytics/01-Command-Line/01-The-Command-Line.html) (similar to this one)
* Software Carpentry's Introductory Lesson on [The Unix Shell](https://swcarpentry.github.io/shell-novice/)
* The Launch School’s [Introduction to the Command Line](https://launchschool.com/books/command_line/read/introduction)
* DHRI’s [Introduction to the Command Line](https://github.com/DHRI-Curriculum/command-line)