---
layout: post
title:      "Twiddle-wakka....WHAT?!?!?"
date:       2018-07-12 20:09:14 +0000
permalink:  twiddle-wakka_what
---


Today, while working on a lab, I ran into the words “twiddle-wakka” in an error for one of the tests. I thought the test case for the lab had swallowed a squirrel or something…what on earth was it talking about?  So I looked it up on Google…and this is what I found:

Twiddle-wakka is the `~>` notation used in gemfiles to define acceptable versions of the gem. [This is the link of the page where I found this information.](https://til-engineering.nulogy.com/posts/a2274133c8-whats-a-twiddlewakka). 


Pretty neat! During my lessons I had come across the nickname “shovel” for the <<  push substitute  (for pushing values on to the end of an array). And also the spaceship operator `<=>` (used by the sort method), so  I knew programmers had nicknames for operators ….but “twiddle-wakka”  takes the cake. Intrigued, I decided to see what other silly names are out there for Ruby operators. These are some of the more interesting nicknames I found: 

### Hashrocket

The `=>` operator that we use for pushing values onto keys when defining hashes is called a “hashrocket”. And is also known as a “fat” or “heavy arrow”. 

### Stabby Lambda

And almost as bizzare as the twiddle-wakka, is the  `->` operator, also known as “stabby lambda”. It is a shortcut for defining a lambda, which I have not come across yet in my lessons, but it appears to be a means of assigning a block to a variable. For example:

```
# Creating a lambda
lambda_new = lambda { |name| "Hello there, my name is #{name}!" }

# Executing the lambda
Lambda_new.call("Fred") # => Hello there, my name is Fred!
```

Apparently you can rework the syntax a little and use the stabby lambda to shorten the code and the execution call:

```
# Creating a lambda using the stabby lambda operator
lambda_new = -> name {puts "Hello there, my name is #{name}!" }

# Executing the lambda using the stabby lambda operator
lambda_new.("Fred") # => Hello there, my name is Fred!
```

Resources on Lambas:  
[Ruby Lambda Shorthand](https://gist.github.com/Integralist/9994331)  
[What are Lambdas in Ruby](https://www.culttt.com/2015/05/13/what-are-lambdas-in-ruby/)

### Birthday Cake Operator

The double pipe equals operator, `||=` has all kinds of nicknames, but my favorite is the birthday cake operator. This operator is used when you want to return a value (if it is defined or not false) or to set the value to something if it isn't defined or is false. Meaning `a ||= b` is either `a`, if `a` is defined, or if `a` is not defined you set it to `b`. 

[More on Birthday Cake Operator](http://www.rubyinside.com/what-rubys-double-pipe-or-equals-really-does-5488.html)

### Elvis

And last but not least…Elvis….is the name given to `?:`,  which is a conditional operator (replaces the if /else syntax). For example:

```
#You can replace this code:
if condition 1
  puts “Condition 1 is true”
else 
 puts “Condition 1 is not true”
end

#With the conditional operator:
Condition 1 ? puts “Condition 1 is true” : “Condition 1 is not true”
```

More Resources on Ruby Operator Nicknames  - Enjoy!   
[Ruby Operator aliases and uses](https://coderwall.com/p/vue87q/ruby-operators-names-aliases-and-uses/)  
[What do you call this in Ruby](https://github.com/JuanitoFatas/what-do-you-call-this-in-ruby)  
[Ruby Operator Nicknames](http://www.benjaminfleischer.com/learning/ruby/operators.html)



