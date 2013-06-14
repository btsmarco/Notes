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
    
    array.each do |item|
        #code
    end

6. .times loop
    
    10.times{ #code }

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

###General
####do...end
In ruby do ... end are used a lot. You can actually use them wherever you can use {} to engulf any block of code. do...end is interchangable with the {}
        
