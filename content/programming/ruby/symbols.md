---
title: "Symbols"
draft: false
---

{{% panel="Symbols" header="Symbols" theme="default" %}}
```ruby
name = "John Smith"

# Change string to a symbol
name.to_sym # = :John Smith
# Value of the string becomes the symbol
name.intern # = :John Smith

# String to symbol
"Hello".to_sym # :Hello

# Symbol to string
:Hello.to_s # "Hello"
```
{{% /panel %}}

{{% panel="Symbols in Hashes" header="Symbols in Hashes" theme="default" %}}
```ruby
person1 = {:name => "John Smith", :age => 20, :gender => "male"}
person2 = {:name => "Jane Doe", :age => 23, :gender => "female"}
```
{{% /panel %}}
