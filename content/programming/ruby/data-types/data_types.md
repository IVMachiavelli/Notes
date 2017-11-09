---
title: "Data Types"
draft: false
---

{{% panel="Variables & Constants" header="Variables & Constants" theme="default" %}}
Following the ruby style guide all Symbols, Methods and Variables should use snake_case.
```ruby
# Variables
first_name = "John"
last_name = "Smith"
```
```ruby
# Constants (defined using all caps)
FIRST_NAME = "John"
LAST_NAME = "Smith"
```
{{% /panel %}}

{{% panel="Strings & Comments" header="Strings & Comments" theme="default" %}}
```ruby
# This is a one line basic comment

=begin
This is a multi-line
comment
=end

```

```ruby
# Escaping goes here
```

```ruby
# Basic string
string = "this is a string"

# multi line string
multiline_string = %q{This is a
multi line string}

# OR (same as above)
multiline_string = %!This is a
multi line string!

# OR
multiline_string = <<ANOTHER_LONG_STRING_LITERAL
this is just another exmaple of
a long string literal
ANOTHER_Long_STRING_LITERAL
```

```ruby
# String methods
"John" + "Smith"  # JohnSmith
"John".capitalize # John
"John".downcase #  john
"John".chop # Joh
"John".next # Joho
"John".reverse # nhoj
"John".sum # 431
"John".swapcase # jOHN
"John".upcase.reverse # NHOJ
```
```ruby
# String substitution
puts "AdamSmith".sub('Adam', 'John')

# Substitute all matching
puts "A random string: 128741469".gsub('1', '5') # replace all 1 with 5
```

```ruby
# Concatenation
puts first_name + last_name

# The << is more efficient when lots of concatenation is used.
puts first_name << last_name

# call the variables directly.
puts "Hello, #{first_name} #{last_name}"

# Using .concat reassigns the first variable, so first_name will become "John Smith"
puts first_name.concat(last_name)

# Strings are sequences of characters in ruby.
puts first_name[3] # = n
puts last_name[0] # = S

# Also can be used directly on a string
puts "This is a number 8164897091"[17..26] # = 8164897091
```
{{% /panel %}}

{{% panel="Ranges" header="Ranges" theme="default" %}}
```ruby
# Simple range
puts ('A'..'Z')

# Range to array, puts 1 to 5.
puts (1..5).to_a

# Negative range to array, puts -4 to 0.
puts (-4..0).to_a

# Subtract the last number, puts numbers 1 to 3.
puts (1...4).to_a

# Range with include
(1..100).include?(14)
```
```ruby
# Range iteration
('A'..'Z').each {|letters| puts letters}

# Iterate range & convert to Array
(10..100).to_a.each {|numbers| print numbers}
```
{{% /panel %}}

{{% panel="Split" header="Split" theme="default" %}}
```ruby
# Simple split of a string, puts each word on a newline
test_string = "This is a string"
puts test_string.split

# Split a date
date = "05/16/1975"
puts date.string('/')
```
{{% /panel %}}

{{% panel="User Input" header="User Input" theme="default" %}}
```ruby
# Get a string
puts "What is your name?"
name = gets.chomp

# Get input & convert to integer
puts "How old are you?"
age = gets.chomp.to_i

puts "Your name is #{name} and you're #{age} old."
```
{{% /panel %}}
