First, you will need to download an IDE such as VS Code, IntelliJ PyCharm or Idea, etc. If you are given the option to add to path, do it. Restarting the terminal may be needed for the change to propagate. For VS Code, install the suggested plug-ins such as PyLance.

# Opening the Workspace

Alternatively, just open your IDE and open the project folder through the GUI. The below is more convenient once you set it up and learn it.

1. Download zip from website, drag and drop it into your folder for this class.
2. Unzip using GUI (or do this as a part of #3 in the terminal).
3. Open your IDE (If you don’t have your IDE added to path, search up how to and add it first, IDE’s often include a GUI option to do it with a few clicks).
   1. Open terminal in the current folder & close current folder.
      - MacOS – set up & use shortcut or GUI: see options in this maketecheasier.com article.
      - Windows – set up & use GUI: add either git bash and/ or Windows Terminal to the context menu for them to show up after right clicking in empty space of a folder. Alternatively, open any terminal, type cd , drag and drop the folder in which the project is (tested with Windows Terminal).
      - Linux – use GUI: right click in your file manager and select open terminal.
   2. Type your ```your_editor .```, i.e. ```code .``` (run program aliased as code in the folder “.”, which is the current directory).
      - This is only for editors that can open folders, such as VS Code (```code .```) and IntelliJ (```pycharm .```) editors. See the Using an IDE section for features you might want to use.
      - If you want to use something like vim or emacs, just keep the terminal open and open files using i.e. ```vi file.py```. Note that you can press tab to get help from autocomplete instead of typing out file names, it’ll look through the possibilities and give as many characters as unambiguous.
4. If your editor has an integrated terminal like VS Code or PyCharm, you can close the terminal. Otherwise, you can ```Alt-Tab``` or ```Cmd-Tab``` to switch between windows.
   - On Windows, you may need to do extra things to get Anaconda working in the integrated terminal, see how to do so for VS code in the Using an IDE section.
   - On Windows, if you can’t get the integrated terminal working: when doing step 3, you need to open an Anaconda prompt, and enter the folder of the project. Doing the latter is described in 3.a.ii. If dragging and dropping doesn’t work, you can also click on the path bar and copy the absolute path.

# Using an IDE

VS Code Windows shortcuts are noted, but other OS’s and most IDE’s should have the same features, so you can look up how to do it in yours. You should try these out in the python basics or the tutorial project; this can save you a lot of time in the future projects.

These are in rough order of usefulness.

- See descriptions of variables. VS Code: ```mouse hover``` to see what a variable is, ```Ctrl- mouse hover``` to see stringdoc or definition, ```Ctrl- mouse click``` or ```f12``` to navigate to definition. Especially helpful for functions, although the IDE may not always figure out the definitions, for instance when PyLance in VS Code can’t figure out what class’s method is getting called.
- Search in all files in project. VS Code: ```Ctrl-Shift-F```. If you want to find what function foo does, search for def foo
- Shortcut for hiding & showing the integrated terminal to free up the screen. VS Code: ```Ctrl-```` (the symbol to the left of 1).
  - In Windows VS Code, you need to do the following to get conda working in the integrated terminal: in the bottom bar on the left, select your conda environment for the class as the Python interpreter. You may need to open a .py file to see this option. Then, open the integrated terminal, and from the dropdown next to the “+” sign, select the command prompt (& close the Powershell). Your environment should automatically activate, you can run ```python -V``` (note the capital V) to check that the Python version is 3.6.
- Debugger (needs a little bit of setup). Set breakpoints where you want them by clicking next to line number on the left, and run the debugger on the autograder.py file. VS Code: open the autograder.py file and press f5. Select Python, make sure your Python 3.6 interpreter is in use, choose “current python file”.
- Auto format code. VS Code: MacOS ```Shift-Option-F```, Windows ```Shift-Alt-F```, Linux ```Ctrl-Shift-I```.
- Search all filenames in project. VS Code: ```Ctrl-P```.
- Search things to you can do in the IDE. VS Code: ```Ctrl-Shift-P```.

# Miscellaneous

Switch between windows: ```Alt-Tab``` on Windows and Linux or ```Cmd-Tab``` on MacOS. Pressing tab more than once chooses a less recent window.
Using multiple desktops to sort open windows.
Browser: ```Ctrl-T``` to open new tab, ```Ctrl-Shift-T``` to re-open the most recently closed tab (repeatable), ```Ctrl-W``` to close the current tab, ```Ctrl-Tab``` and ```Ctrl-Shift-Tab``` to cycle between tabs (Firefox and Chrome are different with this last one).

# Extra reading – What is the path environment variable?

This is not related to course content or the workflow at all.

The OS has many executable files, and it needs the path to the executable to run it. For instance, clicking an icon in program list or taskbar/ dock is just a shortcut – mapping from program name to the location of the file to execute. From the terminal, we can simply navigate into the folder of the executable and run the file, or give the absolute path to the file.

In the terminal, a command consists of first the program, then its options and arguments. If the program part doesn’t have any “/” in it, it is recognized as an attempt to use the Path environment variable.

Path is conceptually a collection of shortcuts for commands. The OS looks for the first word as an executable in the folders given in the Path variable. We simply need to add the folder containing the appropriate program to Path if we want to call if from anywhere.

Anaconda effectively changes what ```python``` corresponds to, pointing it to a different Python interpreter. Furthermore, it keeps that Python interpreter and its installed libraries separate from everything else, all without breaking the Path variable.


