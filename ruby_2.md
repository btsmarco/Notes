#Notes of Ruby 2.0

source: http://www.ruby-doc.org/docs/ProgrammingRuby/html/language.html

####Embedded Documentation
Interestingly enough all the lines between '=begin' and '=end' (without the quotation marks) are ignored by the compiler and are usually used for documentation purposes.

####BEGIN and END blocks
Just as the heading says, you can have multiple BEGIN blocks.

    BEGIN {
        #code here
    }

    END {
        #code here
    }

###General Delimited Input
These are a set of alternative forms of literal strings, arrays, regular exp, and shell commands.

> %q , %Q, %, %w, %r, %x

Google them when needed. A few examples:

    %q(this is a string)
    %Q-this is a string too-
    %x{cd ..}
All the brackets are interchangeable

###Strings

There are a lot of tricks one can do with strings in ruby some of them are

    "\123mile" >> Smile
    %Q!"I said 'nuts',"I said! >> "I said 'nuts'", I said
    %"Try #{a + 1}, not #{a -1}" >> Try 124, not 122
    "This is a string too" >> This is a sting too
    'Con' "cat" 'en' "ate" >> "Concatenate"

You can also find some more points in notes 1.

###Ranges

exp..exp is an inclusive range while,
exp...exp doesn't include the last element in the range.

###Arrays

Nothing really special here.
    
    arr = [ fred, 10, 2.12, "string", barney('pebbles'), ]
    arr = %w( fred wilma barney betty great\ gazoo )
    ##the array will have each word as an element, except for the last 2 words, so 'great gazoo' is the last element in the array.

###Hashes
Hashes in ruby are the python equivalent of dictionaries.

    countries= {"Egypt"=> 'Arabic', "USA"=> 'English'}
    puts countries['Egypt']  #>> Arabic

###Symbols
Symbols are something quite specific for ruby, they might be used in other languages but didn't hear anything about that

I can provide some examples below
    puts :var >> var
    puts :"I am Marco" >> I am Marco
    man = :Augustine
    puts dude >> Augustine
    puts :'num'.object_id >> 294728

Some properties of the symbols are
+ They cannot be changed during runtime
+ They could be used like strings
+ You can never find them on the left side of an assignment

###Regular Expression 
A regular expression may include one or more options that modify the way the pattern matches strings. They are what one uses in cases like this
    
    name = "Marc"
    age = 20
    puts "Hi, this is %s, and I am #{age} years old." %name

You can create your own through the Regexp.new (the object is called Regexp,as you can already see).

Using #{} for substitution is equivalent to using the regular expression '\o', so it is not very different.

###Names

Like any language there are some reserved names, including being, rescue and ensure which -thanks to stackoverflow- are the try, except block in ruby.
    
    begin
        #something that might raise an exception
    rescue SomeExceptionClass => some_variable
        #code deals with this exception
    resuce
        #code that deals with other exceptions (all the rest)
    ensure
        #code that always runs like 'finally' in Java and C#
    end
    #source: http://stackoverflow.com/questions/2191632/begin-rescue-and-ensure-in-ruby

In Ruby names are a little different.

- Local variables are just like anywhere else, it is a combination of certain allowed characters.

- An Instance variable name starts with an "at" sign ('@') followed by a name character.These variables have a larger scope than local variables. In short they are like global variables in other languages (they are usable anywhere in the file).
    
    @name   @Size   @_something

- A class variable name starts with two 'at' sign ('@'). It is usable in multiple connected files

    @@name @@Size @@_anything


