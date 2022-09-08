# Intro to Computer Programming
<img src="https://yakbots.com/wp-content/uploads/2020/09/hitchhikers-guide-to-the-galaxy-dont-panic.jpg" alt="hitchhikers dont panic" width="600"/>

Teacher: Morgan Snyder \
Nueva Upper School, San Mateo CA \
Credit to [Carl Shan](https://github.com/carlshan/intro_to_computer_programming) for original curriculum and [Matt Hesby](https://github.com/MattHesby) for the project curriculum! :tada: 

### Description
This is the repository containing code samples, tutorials, and project starters for the Intro to Computer Programming course at Nueva Upper School.

## Developer Environment Setup
We will be programming in Python this semester, a general purpose programming language that is used for building websites, automating tasks, and data analysis, among other things. We will be using a variety of libraries written in Python, which are collections of prewritten Python code that we can use to make large tasks easier, like drawing with [p5](###project-1-drawing-with-p5) for our first project.

Let's start by preparing your computer to run programs using the latest version of Python! \
⚠*These directions assume that you have learned basic commands in Terminal, which are covered in [these slides](https://docs.google.com/presentation/d/1CojhIzUy_x16zoKOE_BFhZST0xzP3eFsVbdQRhcbuCk/edit?usp=sharing) or you can look at [this cheatsheet](https://github.com/0nn0/terminal-mac-cheatsheet#core-commands) as a refresher.*

1. **Download a code editor!** I recommend [Visual Studio Code](https://code.visualstudio.com/download) or [Atom](www.atom.io). A code editor is like a programmer's iron man suit - It's a text editor with a bunch of special tools programmers.
2. **Install Homebrew.** Homebrew is a package manager for Mac - it's like your personal code librarian. Instructions are also here: https://brew.sh/
   1. Open your Terminal (command + Space then type Terminal)
   2. Copy and paste the following in your Terminal `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"` then hit Return
   3. Enter your password and hit Return (your password will not show up when you type 🙃)
   4. Hit Return again (don't abort 😸)
   5. When Homebrew is done installing, you should see instructions to add the `% brew` command to your Terminal's path. Run the following command in your Terminal: `echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/<your username>/.zprofile
    eval "$(/opt/homebrew/bin/brew shellenv)"` and hit Return
3. **Install Python 3** by running `brew install python3` in your Terminal.
4. **Set Python 3 as your default Python version**
   1. Create a new file by running `vim ~/.bash_profile` in your Terminal
   2. Hit your "i" key to insert text and copy/paste the following in the new file: `alias python="python3"`
   3. Hit the "esc" key to exit insert mode, then type ":wq" (for "write and quit") then hit Return
   4. Finally, run `source ~/.bash_profile` in your Terminal
5. **Verify that things work!**
   1. Run `python -v` in your Terminal. You should see that Python 3.9.6 (or higher) is being currently used
   2. Run `brew help` in your Terminal. You should see the documentation of all brew commands!
   3. Look at [Troubleshooting](###Troubleshooting) below if these commands are not working as expected

#### Troubleshooting
```zsh: command not found: brew```
You need to add the `brew` command to your path, so that Terminal recognizes it! Run this is Terminal:
```
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/<your username>/.zprofile
    eval "$(/opt/homebrew/bin/brew shellenv)"
```
    
```/nofile.py': [Errno 2] No such file or directory```
Make sure you are in the directory that your code lives in! You can use `cd <Directory name>` to go to another Directory in your current folder, or `cd ..` to move up a level in the file hierarchy.
    
## Project 1: Drawing with p5

We'll use p5 for our first project. This library is used for creating visual graphics. Some of you might be familiar with Processing, a visual graphics library in Javascript, and p5 was in fact originally built in Javascript using Processing as a foundation before being translated to Python!

Let's get started by installing p5 on your machine. If you haven't followed the steps to install Homebrew and Python in the [Developer Environment Setup](##Developer Environment Setup) steps, do that **first**!

### Installing p5
Open your Terminal. Run the following commands by typing them in Terminal, then hit Return.
1. `python3 --version` this should return `3.10.6`
2. `pip3 install --upgrade pip` to make sure you're on the latest version of the python package installer
2. `pip3 install p5` this will fail; that’s okay
2. `pip3 install numpy` This installs the latest version of numpy, which is a dependency for p5
3. `pip3 install freetype-py glfw pillow requests skia-python` This installs most of the dependencies that come after numpy
4. `pip3 install pyopengl`
5. `pip3 install vispy --use-deprecated=legacy-resolver` If this fails, run `pip3 install cython` and try again!
6. `pip3 install p5 --no-deps`
7. **Test out that it works!** The p5 library offers many test examples that you can try out [here](https://github.com/p5py/p5-examples) - Bookmark it!
   1. Copy the code from [snake.py](https://raw.githubusercontent.com/p5py/p5-examples/master/misc/games/snake.py)
   2. Create a new file in your Terminal `vim snake.py`
   3. Paste the code into the new snake.py file
   4. Hit "esc" and close by typing ":wq" and hitting Return
   5. Run the program by running `python3 snake.py` in Terminal
   6. You should get a popup window with the game - hit an arrow key on your keyboard to play!

## Writing and running your first p5 program

#### Write your program
1. Create a new file in your code editor by going to **File > New** in the top bar or pressing **⌘(command) + N**. Save the file in your Development folder and call it `something.py` or `whateveryouwant.py` - Just sure it has the `.py` at the end so your computer knows it's written in Python.

Every p5 program follows this recipe:
```
from p5 import *     # this line imports all of the code from the p5 library

def setup()          # the setup function runs once
   #ADD CODE HERE to define settings such as canvas size, fill color, etc.

def draw()           # the draw function runs every frame (~ 60 times per second!)
   #ADD CODE HERE to draw things on the canvas
   
run()                # the run function begins the program, first calling setup() then starts the draw() loop
```
2. Inside your file, copy and paste the p5 boilerplate above and add your own code to the `setup()` and `draw()` functions.

You can reference the [p5 documentation](https://p5.readthedocs.io/en/latest/reference/index.html) or look at some of the [p5 code examples](https://github.com/p5py/p5-examples) for ideas.

#### Run your program
1. Open Terminal. Use your `cd` and `ls` commands to navigate to the directory that your p5 code is saved in.
2. Run the Python program `python3 replace_me.py`
3. Terminate the program by pressing **Ctrl + C** or closing the p5 graphics window. You can also press **⌘(command) + T** to open a new Terminal tab and run your program there (So many p5 windows WOW!)

#### Troubleshooting
`NameError: name 'x' is not defined` you are trying to use a variable before you've declared it. add a line to your code before you use `x` that declares its value, such as `x = 42` or `x = "my string"`. \
`IndentationError: expected an indented block` make sure that you've added code underneath `def setup()` and `def draw()` that is indented. if you're still getting the error, check that the code beneath your `if`, `elif` and `else` statements is indented, check that the code beneath your `for` and `while` loops is indented, check everywhere!
