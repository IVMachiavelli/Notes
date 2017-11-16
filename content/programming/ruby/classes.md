---
title: "Classes"
draft: false
---

Reference: https://www.tutorialspoint.com/ruby/ruby_classes.htm
{{% panel="Understanding Classes" header="Understanding Classes" theme="default" %}}
```text
    Local Variables − Local variables are the variables that are defined in a method. Local variables are not available outside the method. You will see more details about method in subsequent chapter. Local variables begin with a lowercase letter or _

    (@) Instance Variables − Instance variables are available across methods for any particular instance or object. That means that instance variables change from object to object. Instance variables are preceded by the at sign (@) followed by the variable name.

    (@@) Class Variables − Class variables are available across different objects. A class variable belongs to the class and is a characteristic of a class. They are preceded by the sign @@ and are followed by the variable name

    ($) Global Variables − Class variables are not available across classes. If you want to have a single variable, which is available across classes, you need to define a global variable. The global variables are always preceded by the dollar sign ($)
```
{{% /panel %}}

{{% panel="Object Variables" header="Object Variables (Instance Variables)" theme="default" %}}

An object is an instance of a class. If Shape is the class, then X = Shape.new creates a new Shape instance and makes x reference that object. You would then say x is a Shape object, or an object of class Shape.

Object variables (also known as instance variables) are so named becuase they have scope within, and are associated to, the current object.
```ruby
# A class with object variables (instance variables)
# A class with two methods
class Square
  # initialize is a special method that's called when a new object based on that class is created.
  # initialize accepts a single argument side_length
  def initialize(side_length)
    # Object variables are prefixed with a @ and can now be accessed from any other method inside that object.
    @side_length = side_length
  end

  def area
    @side_length * @side_length
  end
end

# Using the Square class
# a and b pass arguments (10) and (5) to side_length
a = Square.new(10)
b = Square.new(5)
puts a.area
puts b.area
```

{{% /panel %}}

{{% panel="Global Variables" header="Global Variables" theme="default" %}}
Global variables should be avoided and only used when absolutely  necessary.
```ruby
# Using Global variables with $
def basic_method
  puts $x
end

# $x is a global variable and can be called anywhere in your application.
$x = 10
basic_method  
```
{{% /panel %}}

{{% panel="Class Variables" header="Class Variables" theme="default" %}}
Class variables are particularly useful for storing information relevant to all objects of a certain class. For Example, you could store the number of objects created so far in a certain class using a class variable like so.
```ruby
class Square
  def initialize
    # Since @@number_of_squares is a class variable, it's already defined each time you create a new object (except for the first time, but that's why you check to see if it's defined, and if not, give it an initial value of 1)
    if defined?(@@number_of_squares)
      @@number_of_squares += 1
    else
      @@number_of_squares = 1
    end
end

def self.count
  @@number_of_squares
end
end

a = Square.new
b = Square.new

puts Square.count
```
{{% /panel %}}
{{% panel="Class Methods vs Object Methods" header="Class Methods vs Object Methods" theme="default" %}}
Class Methods perform functions related to the class, but not necessary a particular object of that class.
```ruby
class Square
  # Class method
  # self defines the method as being specific to the class. With no prefix methods are automatically instance methods.
  def self.test_method
    puts "Hello from the square class!"
  end

  # Instance Method
  def test_method
    puts "Hello from an instance of a class Square"
  end
end

Square.test_method
Square.new.test_method
```

```ruby
# You can also write the class method above like this
class Square
  def Square.test_method
    puts "Hello from the Square class!"
  end
end
```
{{% /panel %}}

{{% panel="Inheritance" header="Inheritance" theme="default" %}}
```ruby
class ParentClass
  def method1
    puts "Hello from method1 in the parent class"
  end

  def method2
    puts "Hello from method2 in the parent class"
  end
end

# ChildClass inherits from ParentClass
class ChildClass < ParentClass
  def method2
    puts "Hello from method2 in the child class"
  end
end

my_object = ChildClass.new

my_object.method1 # From ParentClass
my_object.method2 # From ChildClass
```

```ruby
class Person
  def initialize(name)
    @name = name
  end

  def name
    return @name
  end
end

class Doctor < Person
  # Overides name from Person class.
  def name
    # super looks up the inheritance chain and calls the method of the same name on the next highest class. Using super within the name method in Doctor then uses the name method in Person.
    "Dr. " + super
  end
end
```
{{% /panel %}}

{{% panel="Overriding Classes" header="Overriding Existing Classes" theme="default" %}}
```ruby
x = "This is a test"
puts x.class
puts x.length
puts x.upcase
```
```text
String
14
THIS IS A TEST
```
Now lets override x
```ruby
class String
  def length
    20
  end
end

puts "This is a test".length
puts "a".length
puts "A really long line of text"
```
```text
20
20
20
```
Overriding methods
```ruby
class Dog
  def talk
    puts "woof!"
  end
end

class Dog
  def talk
    puts "Howl!"
  end
end

my_dog = Dog.new
my_dog.talk
```
```text
Howl!
```
{{%/panel%}}

{{% panel="Reflection" header="Reflection" theme="default" %}}
Reflection is the process by which a computer program can inspect, analyse and modify itself while running and being used.
```ruby
a = "This is a test"
puts a.method.join(' ')
```
{{% /panel%}}

{{% panel="Encapsulation" header="Overriding Existing Classes" theme="default" %}}
Encapsulation is the ability for an object to have certain methods and attributes available for use publicly.
```ruby
```
{{% /panel %}}

{{% panel="Singleton" header="Singleton" theme="default" %}}
```ruby
class TableCorporation
end

class << TableCorporation
  ...
end
# --- OR ---
class TableCorporation
  class << self
    ...
  end
end
```
{{% /panel %}}
