# Intro to Computer Programming
<img src="https://yakbots.com/wp-content/uploads/2020/09/hitchhikers-guide-to-the-galaxy-dont-panic.jpg" alt="hitchhikers dont panic" width="600"/>

Teacher: Morgan Snyder \
Nueva Upper School, San Mateo CA \
Credit to [Carl Shan](https://github.com/carlshan/intro_to_computer_programming) for original curriculum! :tada:

### Description
This is the repository containing code samples, tutorials, and project starters for the Intro to Computer Programming course at Nueva Upper School.

## Developer Environment Setup

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
   1. Create a new file by running `vim bash_profile` in your Terminal
   2. Hit your "i" key to insert text and copy/paste the following in the new file: `alias python="python3"`
   3. Hit the "esc" key to exit insert mode, then type ":wq" (for "write and quit") then hit Return
   4. Finally, run `source bash_profile` in your Terminal
5. **Verify that things work!**
   1. Run `python -v` in your Terminal. You should see that Python 3.9.6 (or higher) is being currently used
   2. Run `brew help` in your Terminal. You should see the documentation of all brew commands!
   3. Look at [Troubleshooting](###Troubleshooting) below if these commands are not working as expected

### Troubleshooting
```zsh: command not found: brew```
You need to add the `brew` command to your path, so that Terminal recognizes it! Run this is Terminal:
```
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"' >> /Users/<your username>/.zprofile
    eval "$(/opt/homebrew/bin/brew shellenv)"
```
    
```/nofile.py': [Errno 2] No such file or directory```
Make sure you are in the directory that your code lives in! You can use `cd <Directory name>` to go to another Directory in your current folder, or `cd ..` to move up a level in the file hierarchy.
    

