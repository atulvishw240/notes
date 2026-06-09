## Basics 

`atul@atul$` is the prompt

`echo "hello"` - prints hello

Note: When Ctrl-C fails, 90% of the time hitting ESC (escape) will do the trick.

`man [command]` - to know more about command

`CTRL + A` - move to the beginning of line
`CTRL + E` - move to the end of the line
`CTRL + U` - delete to the beginning of the line
`clear or CTRL + L` - clears the terminal
`exit or CTRL + D` - exits the terminal

## Manipulating Files

`echo "From fairest creatures we desire increase," > sonnet_1.txt`    -     Here the right angle bracket > takes the string output from echo and redirects its contents to a file called `sonnet_1.txt`.

`echo "That thereby beauty's Rose might never die," >> sonnet_1.txt`  -   This just adds the line to the end of the given file.  (`>>` append operator)

`ls` - list files and directories
`ls *.txt` - to list all files ending in `.txt`
`touch [name]` - creates an empty file with name `name`

`mv test test_file.txt` -  Rename file test to `test_file.txt`.  The name “move” comes from the general use of `mv` to move a file to a different directory

`cp test_file.txt second_test.txt` -  copies content of `test_file.txt` to `second_test.txt` 
`rm second_test.txt` - delete file

![[unix-commands.png]]

## Inspecting files

`which curl` - looks to see if the given program is available at the command line
`CTRL + R` - interactively search through your previous commands
`head sonnets.txt` - shows first 10 lines
`tail sonnets.txt` - shows last 10 lines
`wc sonnets.txt` - shows lines, words and bytes
`head sonnets.txt | wc`  -  `wc` can also take input from "standard in"
`less sonnets.txt` - shows content of the file (`G` end of file, `1G` start of file)
>`CTRL + F` - move forward one page, `CTRL + B` - move backward one page

### Grepping

`grep rose sonnets.txt` - return all lines in `sonnets.txt` that contains "rose"

>`grep` is case insensitive by default. Use `-i` for case insensitive meaning

`!n` - executes the nth command in the command history

`sudo apt update && sudo apt upgrade` - The difference is that commands separated by && run only if the previous command succeeded

`mv foo/ bar/` - renames foo directory to bar
`cp -r ../text-files .`  - copy the directory and all its content recursively in the current directory
`rm -rf dir/` - removes `dir`, its files, and any sub directories without confirmation

I understand the joke now 
`sudo rm -rf /` will delete everything, even your operating system