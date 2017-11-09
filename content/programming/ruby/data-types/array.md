---
title: "Array"
date: 2017-10-25T06:03:55-04:00
draft: false
---

{{% panel="Array" header="Array" theme="default" %}}
```ruby
# Creating an array
random_array = ["Random", 1, 2, 3, "Array"]
```
```ruby
# puts first element
puts random_array.first
puts random_array[0]
```
```ruby
# puts first three elements in the array
puts random_array.first(3)
```
```ruby
# puts the last element
puts random_array.last
puts random_array[4]
puts random_array[-1]
```
```ruby
# puts the last three elements
puts random_array.last(3)
```
```ruby
# Joining array elements
random_array.join # = Random123Array
random_array.join(' ') # = Random 1 2 3 Array
```
```ruby
# Reassign an Array
random_array[-1] = "Replaced" # Replaced "Array" with "Replaced"
```
```ruby
# Add a element to the end of an Array
random_array.push("Push")
random_array << "Push" # same as above
```
```ruby
# Remove an element from the end of an Array
random_array.pop # Removes "Array"
```
```ruby
# Delete an array element by index
random_array.delete_at(0) # Deletes "Random"
```
```ruby
# Delete by element
random_array.delete("Array")
```
```ruby
# Get array count
puts random_array.count # = 5
```
```ruby
# Adding arrays together
first_array = ["John", "Smith"]
second_array = ["Jane", "Doe"]
third_array = first_array + second_array
```
```ruby
# Subtract arrays
fourth_array = third_array - second_array
puts fourth_array
```
{{% /panel %}}

{{% panel="Array iteration" header="Array iteration" theme="default" %}}
```ruby
# Collect iterates an array by element and assigns to that element the result of the expression.
[1, 2, 3, 4, 5, 6].collect {|numbers| puts numbers * 10} # = 10 20 30 40 50 60
```
```ruby
# Iterating over an array with each
array = ["Joe", "John", "Smith", "Jane", "Becky"]
array.each do |first_name|
  puts "First name: #{first_name}"
end

# same as above
array.each {|first_name| puts "First name: #{first_name}"}
```
```ruby
# Create an array with each
new_array = []
(0..10).each do |i|
  puts "Adding #{i} to the array"
  new_array.push(i)
end

new_array.each {|i| puts "New array:#{i}"}
```
```ruby
# iterating with a for loop
another_array = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
for i in another_array; puts "New array:#{i}; end"
```
```ruby
# iterating a multidimensional Array
multi_array = [["bob", "John", "Matt"], [23, 35,13], ["red", "yellow", "blue"]]
multi_array.each do |sub_array|
    sub_array.each do |x|
    puts x
    end
end
```
{{% /panel %}}
