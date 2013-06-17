Welcome to the ruby notes 3
---
###Loops
There are a number of loops in ruby:
1.for loop
2.until loop
    
    until conditional do
        #code
    end
    
    begin
        #code
    end until conditional

3.while loop
4.loop do....end
    
    loop do
        #code
    end

5. .each loop
The .each loop doesn't mutate the array and returns the same array, unlike other block that can do either or both.
.each only touches elements. It does nothing else.
    
    array.each do |item|
        #code
    end

6. .times loop
    
    10.times{ #code }

7. .collect loop

.collect is a powerful block because one can return a new array that is different by using .collect only or by adding '!' to it ('.collect!') which will mutate the array itself and return the new mutated array.

8. .select loop

This loop returns an array of the variables that passed the conditional inside the block only.

####Control flow in loops

Interesting enough ruby has more than break and continue to control the flow in a loop.
Next, redo and retry are also used in ruby.

#####next
next is used to skip a certain condition

    i = 0 
    loop do
        next i % 2 == 0
        print #{i}
        i = i + 1
        break if i > 25
    end

### Procs and BLocks

Blocks are any set of instructions between { } or do ... end. They can be used and reused through out the code, they can be passed to methods that has yield like

    def TheMethod 
        yield
    end
    TheMethod { puts "This is actaully interesting }
    
    >> This is actually interesting 

While Blocks are nameless, Procs have names which allows them to be reused easily in the code. They are initialized by 
    
    NewSetOfCode = Proc.new { |var| #do something to var } 

To pass it to methods (that have yield) you need to add '&' infront of it
    
    Method( &Proc )

One can turn a symbol into a proc by adding '&' before it like

    strings = ["1","2"]
    nums = strings.collect(&:to_s)

### Lambdas

Lambdas are a set of code that is very similar to Procs except that it cares about how many arguments you pass to it and it returns back to the method it was called from.

    NewL = lambda { |something| #Use that something here }

###General
####do...end
In ruby do ... end are used a lot. You can actually use them wherever you can use {} to engulf any block of code. do...end is interchangable with the {}
        
