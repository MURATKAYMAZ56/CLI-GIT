# CLI  (Command language Interpreter)
## Command line
The command line (cli, shell) is the interface between  user and the operating system which interprets the commands and allows the computer to respond to the command.


## General syntax
`command_name param1 param2 [OPTIONS]`
In the above, square brackets denote the optional part of the command.
The square brackets are not supposed to be typed.
`param1` and `param2` are COMPULSORY parameters.
## Some commonly used commands

`ls` - show the contents of the directory. `ls -a` will show all hidden files. `ls -l` will show more files in long format (more details)

`pwd` - print the Present Working Directory. What directory am I in? 

`cd` - change directory to the one specified. If no directory is specified this will take you to your home directory. Remember that `.` is the current directory and `..` is the parent directory. So `cd .` changes the directory to the current directory (does nothing!). 

`echo` - prints the string on screen (on desktop/bash terminal).

`cat` - print the contents of the file - this will print the WHOLE file. If you want to pause printing after a full screen use the below command.

`less` - show one screen full of the file (spacebar/Enter moves forward and q stops printing)

`head` - show the beginning of a file e.g. `head -3` shows the first 3 lines of the file

`tail` - show the end of a file `tail -4` shows the last 4 lines of the file

`wc` - show the word count of a file (prints number of lines, words and characters in the file)

`CTRL-c` - stop what is happening on the command line 

`CTRL-z` - hard stop what is happening on the command line 

`mkdir` - create a new directory

`touch` - create an empty file

## Output redirection

```
$ echo "Hello"
Hello
```
will display the string Hello on the terminal.

```
$ echo "Hello" > greetings.txt
```
Will redirect the output of the echo command to the file "greetings.txt".

```
$ echo "Bye World!" >> greetings.txt
```
Will APPEND the output of the echo command to the file "greetings.txt"


## Input Redirection

```
$ sort < numbers.txt
```
Will read the contents from the file "numbers.txt" and sort them. By default, sort will sort the lines alphabetically.

`sort -n < numbers.txt` will sort the lines numerically.


## Pipe
With pipes, the output of one command is sent to the next command as an input.
```
$ cat some-big-file | more
```
This will provide contents of the file "some-big-file" as an input to the command "more". more is a pager utility. The more command breaks the output into individual screens and waits for you to press the space bar before continuing on to the next screen. Pressing the enter key will advance the output one line.

```
$ cat numbers.txt | sort | uniq
```
This will find out all the unique numbers from the file "numbers.txt". Note that, the file must contain numbers on separate lines.

```
$ cat numbers.txt | grep 3
```
This command is the easiest way to find something in the file. It's useful for watching logs, in combination with `tail`. The `grep` command is used to search text. It searches the given file for lines containing a match to the given strings or words. 

# For loop
In bash, it is possible to write a loop
that iterates over a range of numbers.
```
SYNTAX:
for VAR in {START..END}; do COMMAND1 [;COMMAND2 [;COMMAND3]]; done
```

_for_,  _in_, _do_, _done_ are keywords.
Curly brackets ('{' and '}')are the part of the syntax.
VAR takes values from START to END with the step of 1.
There must be at least one command after _do_.
Square brackets ('[' and ']') denote that more commands are optional.
To use VAR in command(s), '$' symbol must be used before it.
```
EXAMPLE:
$ for i in {1..10}; do echo $i; done
```
Here, **i** is the loop variable. Any other character or a sequence of characters can be used instead of **i**.
i takes the values 1,2,3, until 10. We are using a simple command `echo $i` to print these values.

# vim
vim is an editor (like notepad on windows)
Sometimes it is a little hard to remember all the vim commands so here is a handy cheatsheet: https://www.fprintf.net/vimCheatSheet.html - with practice it will not seem so odd. 

`vim <filename>` will open a file in vim
When you are in vim there are two modes:
1. Insert mode - in this mode you can enter and change text
2. Command mode (also called escape mode) - in this mode you can issue commands to vim

When you are in vim `a` and `i` will put you in insert mode and `esc` will take you our of insert mode. If you get stuck in vim press `esc esc` (yes, twice) and then `:q` and this will take you back to the shell. Some commands we covered: 

`a` = Go to insert mode

`<ESC> :q` = quit file 

`<ESC> :wq` = save file and quit vim

`<ESC> :q!` = exit vim without saving

`<ESC> yy` = copy current line (the line you are on)

`<ESC> p` = paste what you last copied

Many commands can be preceeded by a number to repeat their action. For example, `<ESC> 4yy` copies 4 lines starting from where you entered the command. 

