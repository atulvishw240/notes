
The `irb` utility ships with Ruby and is the most widely used Ruby command-line tool other than the interpreter itself.

## The variety of Ruby identifiers

- Variables
  - Local
  - Instance - @
  - Class - @@
  - Global -$(anything, even /, ;)
- Constants
- Keywords
- Method names

`x = 100.to_i` means, send the 'to_i' message to 100.

In Ruby, it's more correct to say that you send a message to a receiving object, and the object executes the corresponding method.

Conveniently, the Ruby interpreter can check programs for syntax errors without running the programs. It reads through the file and tells you whether the syntax is okay. To run a syntax check on your file, do this: `$ ruby -cw c2f.rb` The -cw command-line flag is shorthand for two flags: -c and -w. The -c flag means check for syntax errors. The -w flag activates a higher level of warning: Ruby will fuss at you if you’ve done things that are legal Ruby but are questionable on grounds other than syntax.

Assuming you’ve typed the file correctly, you should see the message `Syntax OK` printed on your screen.

Pg no. 15 Reading from a file se padhna hai