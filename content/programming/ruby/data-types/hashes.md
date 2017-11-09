---
title: "Hashes"
date: 2017-10-25T05:59:31-04:00
draft: false
---

{{% panel="Hashes" header="Hashes" theme="default" %}}
```ruby
# Hashes use key value pairs and can be called just like arrays.
months = Hash[1 => "Jan", 2 => "Feb", 3 => "Mar", 4 => "Apr", 5 => "May"]

# Call the hash key
puts months[4] # = Apr

# Hash length
puts months.length # = 5

# Hash Values
puts months.values # puts all values (Jan Feb Mar Apr May)

# Hash Keys    
puts months.keys # puts all keys (1 2 3 4 5)   

# Change Hash Value
months["5"] = "unknown" # Change month of May to unknown

# Is the hash empty?
puts months.empty? # = false

# Does the key exist?
puts months.key?(5) # = true

# Does the value exist?
puts months.value?("May") # = true

# Delete a hash value
months.delete(5) # = Deletes May

# Conditionaly delete hash element
months.delete_if {|key, value| key == 5} # Deletes "May"

# Iterating through hash elements
months.each {|key, value| puts "#{key} is #{value}"}

# hashes inside hashes
people = {
    'john' => {
        'name' => 'John Smith',
        'age' => 30,
        'gender' => 'male',
        'hobbies' => ['running', 'programming', 'linux']
    },
    'jane' => {
        'name' => 'Jane Doe',
        'age' => 30,
        'gender' => 'female',
    }
}

# puts on the above nested hash
puts people['john']['age']
puts people['john']['hobbies']
puts people['jane']['age']
puts people['jane']
```
{{% /panel %}}
