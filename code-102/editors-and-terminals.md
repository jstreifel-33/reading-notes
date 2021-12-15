# Understanding Text Editors

A text editor is exactly what it sounds like: a tool used to edit text. For coders, the text we're editing is our code, so it helps to have a tool that fits that purpose. Most computer OS's will include a barebones text editor such as **Notepad** (windows) or **Text Edit** (Mac). While these basic text editors are perfectly functional and can absolutely be used for writing code, there are more advanced tools available with helpful quality of life features aimed at making coding a more comfortable experience.

Additional features of third part applications include:
- Code completion - many text editors will offer suggestions as you type, allowing you to select and fill a function without having to fully type it out. Code completion will also often close parentheses and brackets as you open them.
- Syntax highlighting - Objects, functions, comments, and other components of your code will be highlighted to allow quick distinctions between different parts of your code. A color-coded breakdown of your code can greatly assist when trying to track down bugs or errors.
- Themes - While basic text editors generally offer a black on white aesthetic, many third part apps offer a variety of themes that change the color scheme of the entire workspace. This can help cut down on eye fatigue, or be tailored to match your mood as you see fit.
- Extensions - One of the single biggest advantages of third party text editors is the existence of **extensions**. These allow for effortless integration of a variety of tools and enhancements to your editor. Often if you can think of a tool that would help your process, someone in the community has also had the idea and created an extension to do just that. Exploring and installing extensions can take your text editor to the next level.

These are just a few of the tools that make third party text editors a much more appealing options for coders when compared to basic text editors. That's not to say that there is anything wrong with using a basic editor. If that's your thing, go for it. If you're interesting in third party editors, [VS Code](https://code.visualstudio.com/) is an option from Microsoft that would make a great starting point.

# Terminal Use and You (a cheat-sheet)

The **Terminal** of your computer is the interface between you and your system. Many people may know it as the "command prompt" but "Terminal" is how we'll refer to it going forward. It'll take some getting used to but here are some useful commands to remember when navigating your system:

`pwd` - "print working directory" will show where you are currently working, such as /users/yourname

`ls [options] [location]` - "List" will print a list of a location's contents. Alone, it will print the current directory. </br>
`ls a` can be used to include hidden files in a list. Hidden files and directories start with a .(dot)

`cd` - will return you to your home directory.

`cd [location]` - will navigate you to a new location of your choosing

### Navigating locations:

When trying to point to or find a location, the following can help navigate:
- **~(tilde)** refers to your **home** directory. `~/Documents` will indicate the Documents folder in /users/yourname. (remember `cd` can be used to return home, and `pwd` will print your current directory!)
- **.(dot)** refers to your **current** directory. If you're home, this will refer to home. If you're in ~/Documents and want to point to /users/yourname/documents/somthing.txt, you can just type `./something.txt`
- **..(dot dot)** refers to parent directory. If you're in /users/yourname/documents, `../something.txt` will point to something.txt in the /users/yourname directory.

### Pathing: Relative vs. Absolute

There are two ways to call out a location:

**Relative Pathing** is used to type a location relative to our current location. If we're in our home directory and we want to a list of the contents of Documents, we can save time and just type the command `ls Documents`. The terminal will list the contents of the directory /users/yourname/Documents since it looks where we currently are.

**Absolute Pathing** doesn't allow for interpretation, and is used to point to a specific location regardless of our place in the system. If we again wanted to list Documents, but we're outside of our home directory, we could instead type `ls /users/yourname/Documents` to accomplish the same thing.

### Other things of note:

**Case Sensitivity** matters. Commands, files, and paths have specific capitalization. Be mindful of these and ensure that you use the correct case when working in the terminal.

**Spaces don't play nice** in terminal. Spaces are how we separate commands, options, and names. If the file or directory you're trying to access has a space, either place it in quotes `~/Documents/'some folder'` or use an **escape character** to ignore the terminal function of a space `~/Documents/some\ folder`

**On Linux everything is a file.** It's files all the way down with Linux. This isn't the case in MacOS but is worth remembering if you have to work with Linux in the future.
