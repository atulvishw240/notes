
![[file-system.png]]

- A shell is a program whose primary purpose is to read commands and run other programs.
- `whoami` - returns your username
- `$` - is a prompt, indicating that the shell is waiting for input

**Help for built-in commands**: 
`man cd` returns "No manual entry for `cd`" because `cd` command is built into the **Bash** shell, rather than existing as separate programs on the file system.

To navigate through the `man` pages, you may use `↑` and `↓` to move line-by-line, or try `b` and `Spacebar` to skip up and down by a full page. To search for a character or word in the `man` pages, use `/` followed by the character or word you are searching for. Sometimes a search will result in multiple hits. If so, you can move between hits using `N` (for moving forward) and `Shift+N` (for moving backward).

![[prompt-structure.png]]


>[!question] When would you use **touch** vs **nano** to create a file?
Use touch when you want to create empty files for other programs to use.

## Commands

- `cp [old] [new]` copies a file.
- `mkdir [path]` creates a new directory.
- `mkdir -p` :  The `-p` option allows `mkdir` to create a directory with nested subdirectories in a single operation `$ mkdir -p ../project/data ../project/results`
- `mv [old] [new]` moves (renames) a file or directory.
- `rm [path]` removes (deletes) a file.
- `cd ~` - Home directory
- `cd -` : Brings back
- `cd ..` : Brings up
- `ls` - list the contents of the current directory
- `pwd` - prints working directory
- `Ctrl + L` or `clear` - Clear the terminal
- `[command-name] --help` -  more info about the command
- `man [command]` - opens man page of command


