---
title: "Control Flow"
date: 2017-10-24T22:09:05-04:00
draft: false
---


{{% panel="Predicates" header="Predicates" theme="default" %}}
```ruby
# Check all possible predicates
puts 0.methods.sort

# Is it odd?
puts 3.odd? # true

# Is it even?
puts 5.even? # false

# Is it between
puts 3.between?(2,5) # true

# Does it start with (case sensitive)
name = "John Smith"
puts name.start_with?("j") # false

# Is it zero?
puts 0.zero? # true

# Is it an integer?
puts 1.integer? # true
puts 3.5.integer? # false

# Does it include
puts [1,2,3,4,5].include?(6) # false

# Arrays
array = [1, 2, 3, 4]

# Is the array empty?
puts array.empty?
```
{{% /panel %}}


{{% panel="Looping & Conditionals" header="Looping & Conditionals" theme="default" %}}
```ruby
# Basic one line loops
# times
5.times do puts "Loop" end # puts Loop 5 times
# upto  
1.upto(10) do puts "Loop" end # puts Loop 10 times
# Step
0.step(100, 10) do puts "Loop" end # puts Loop 10 times by stepping 10 until 100.

# More examples of one line loops
10.times{puts "loop"}
1.upto(10){|i| puts "Count #{i}"}
0.step(100,10){|i| puts "Count #{i}"}
```
```ruby
# Looping with a variable number
1.upto(10) {|number| puts number} # puts number 10 times

# OR (same as above)
1.upto(10) do |number|
    puts number
end
```

```ruby
# Single line if statement
puts "Less than 10" if 10 < 15

# Same as above
something = 10
if something < 15
    puts "Less than 10"
end
```
```ruby
# While statement
x = 1
while x < 100
    puts x
    x = x * 2
end

# Same as above using until
x = 1
until x > 99
    puts x
    x = x * 2
end
```

```ruby
# for loop
for i in 0..4
  puts "#{i}"
end

# Same for loop but with break
for i in 0..4
  if i>3 then
    break
  end
  puts "#{i}"
end

# Same for loop with next
for i in 0..4
  if i < 3 then
    next
  end
  puts "#{i}"
end
```

```ruby
# Using unless
puts "Less than 10" unless 10 >= 15

# same as above
things = 10
unless => 15
    puts "You don't have enough things"
    exit
end
```
```ruby
# else statement
things = 10
if things < 25
    puts "You don't have enough things"
    else
    puts "Yay you have enough things"
end
```
```ruby
# ? ternary operator
things = 12
question = things < 23 ? "No" : "Yes"
puts "Do you have enough things" + question

# Understanding the ternary operator syntax
<condition> ? <result if condition is true> : <result if condition is false>
```

```ruby
# elseif & Case statements
fruit = "orange"
color = "orange" if fruit == "orange"
color = "green" if fruit == "apple"
color = "yellow" if fruit == "banana"

# Same as above using elseif
fruit = "orange"
if fruit == "orange"
    color = "orange"
elseif fruit == "apple"
    color = "green"
elseif fruit == "banana"
    color = "yellow"
else
    color = "unknown"
end

# Same as above using case statement
fruit = "orange"
color = case fruit
    when "orange"
    "orange"
    when "apple"
    "green"
    when "banana"
    "yellow"
    else
    "unknown"
end
```
{{% /panel %}}
