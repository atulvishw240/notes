
Ruby is a programming language. The lowercase version, ruby, is a computer program. Specifically, it’s the Ruby interpreter, the program that reads your programs and runs them. The `irb` utility ships with Ruby and is the most widely used Ruby command-line tool other than the interpreter itself.

## The variety of Ruby identifiers

- Variables
  - Local - first_name
  - Instance - @first_name
  - Class - @@first_name
  - Global -$FIRST_NAME (anything, even /, ;)
- Constants - FIRST_NAME
- Keywords
- Method names

## Method calls, messages, and Ruby objects

`x = 100.to_i` means, send the 'to_i' message to 100.

In Ruby, it's more correct to say that you send a message to a receiving object, and the object executes the corresponding method.

For now, just be aware that although every object has a class, the class of an object isn’t the sole determinant of what the object can do.

The Ruby interpreter can check programs for syntax errors without running the programs. It reads through the file and tells you whether the syntax is okay. To run a syntax check on your file, do this: 
`$ ruby -cw c2f.rb` 

The -cw command-line flag is shorthand for two flags: -c and -w. The -c flag means check for syntax errors. The -w flag activates a higher level of warning: Ruby will fuss at you if you’ve done things that are legal Ruby but are questionable on grounds other than syntax.

> If you ask `puts` to print a line that already ends with a newline, it doesn’t bother adding one.



Page 17 se padhna hai