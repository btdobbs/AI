# Unix Basics – File/ Directory Manipulation[^1]

Windows note: similar commands are available, and things like git bash will have Unix commands.

When you open a terminal window, you’re placed at a command prompt:

```sh 
[~]%
```

The prompt shows your username, the host you are logged onto, and your current location in the directory structure (your path). The tilde character is shorthand for your home directory. Note your prompt may look slightly different. To make a directory, use the ```mkdir``` command. Use ```cd``` to change to that directory:

```sh
[~]% mkdir foo
[~]% cd foo
[~/foo]%
```

Use ```ls``` to see a listing of the contents of a directory, and ```touch``` to create an empty file:

```sh
[~/foo]% ls
[~/foo]% touch hello_world
[~/foo]% ls
hello_world
[~/foo]% cd ..
%
```

Download [python_basics.zip](https://github.com/btdobbs/AI/blob/main/Project/python_basics.zip) into your home directory (note: the zip file’s name may be slightly different when you download it). Use unzip to extract the contents of the zip file:

```sh
[~]% ls *.zip
python_basics.zip
[~]% unzip python_basics.zip
[~]% cd python_basics
[~/python_basics]% ls
foreach.py
helloWorld.py
listcomp.py
listcomp2.py
quickSort.py
shop.py
shopTest.py
```

Some other useful Unix commands:

- ```cp``` copies a file or files
- ```rm``` removes (deletes) a file
- ```mv``` moves a file (i.e., cut/paste instead of copy/paste)
- ```man``` displays documentation for a command
- ```pwd``` prints your current path
- ```xterm``` opens a new terminal window
- ```firefox``` opens a web browser
Press ```Ctrl-c``` to kill a running process
Append ```&``` to a command to run it in the background
- ```fg``` brings a program running in the background to the foreground

# The Emacs text editor

Emacs is a customizable text editor which has some nice features specifically tailored for programmers. However, you can use any other text editor that you may prefer (such as ```nano``` ```vi```, ```pico```, or ```joe``` on Unix; or Notepad on Windows; or TextWrangler on OS X; and many more).

To run Emacs, type ```emacs``` at a command prompt:

```sh
[~/python_basics]%  emacs helloWorld.py &
[1] 3262
```

Here we gave the argument ```helloWorld.py ``` which will either open that file for editing if it exists, or create it otherwise. Emacs notices that this is a Python source file (because of the ```.py``` ending) and enters Python-mode, which is supposed to help you write code. When editing this file you may notice some of that text becomes automatically colored: this is syntax highlighting to help you distinguish items such as keywords, variables, strings, and comments. Pressing Enter, Tab, or Backspace may cause the cursor to jump to weird locations: this is because Python is very picky about indentation, and Emacs is predicting the proper tabbing that you should use.

Some basic Emacs editing commands (```C-``` means “while holding the Ctrl-key”):

- ```C-x C-s``` Save the current file
- ```C-x C-f``` Open a file, or create a new file it if doesn’t exist
- ```C-k``` Cut a line, add it to the clipboard
- ```C-y``` Paste the contents of the clipboard
- ```C-_``` Undo
- ```C-g``` Abort a half-entered command

You can also copy and paste using just the mouse. Using the left button, select a region of text to copy. Click the middle button to paste.

There are two ways you can use Emacs to develop Python code. The most straightforward way is to use it just as a text editor: create and edit Python files in Emacs; then run Python to test the code somewhere else, like in a terminal window. Alternatively, you can run Python inside Emacs: see the options under “Python” in the menubar, or type ```C-c !``` to start a Python interpreter in a split screen. (Use ```C-x o``` to switch between the split screens, or just click if ```C-x``` doesn’t work).

[^1]: [Berkeley Computer Science](http://ai.berkeley.edu)
