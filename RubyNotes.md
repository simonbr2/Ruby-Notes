# Ruby Notes

### Intro Topics

##### Method 

a reusable section of code defined with the `def` keyword followed by the method name and ending with the `end` keyword.

##### Block

a section of code defined within the keywords `do` and `end` or with curly braces `{ }`. 

##### Code Comments

single line comments start with a `#` 
double line comments start with `=being` and end with `=end`

##### Simple Object Methods

`var = "string"`
`var.length` = length of the string
`var.reverse` = string reversed
`var.upcase` = string converted to all uppercase letters
`var.downcase` = string converted to all lowercase letters



### Flow Control

##### If/Else

```print "enter a number: "
num = gets.chomp
num = num.to_i;
 
if num == 5
 print "number is 5"
elsif num == 10
 print "number is 10"
elsif num == 11
 print "number is 11"
else
 print "number is something other than 5, 10, or 11"
end
```

##### Logic

`&&` is a logical operator in ruby which evaluates to `true` if both expressions on either side evaluate to `true`.

`||` is a logical operator in ruby which evaluates to `true` if either expression on either side evaluates to `true`

`Unless` is a statement used in ruby to evaluate an expression. if the expression evaluates to `false` then the code following `unless` is executed



### Looping

`next` can be used within a loop to pass over the following iteration. `next` is followed by an if statement which defines what to skip.

```for i in 1..10
for i in 1..10
  next if i % 2 == 0
  puts i
end
```

`while` loops will run a block of code repeatedly as long as the condition is `true`.

`times` will execute a block of code a specific number of times.

`until` loops will run as long as the condition remains `false`. when the condition becomes `true` the loop will stop.



### Arrays

an **array** is an ordered collection separated by commas and enclosed by [ ]. Arrays can contain different types of objects.

```numbers = [1, 2, 3, 4, 5]
numbers = [1, 2, 3, 4, 5]
#An array of Integers
 
words = ["See", "Spot", "run"]
#An array of Strings
 
mixed = ["hello", 5, true, 3.0]
#An array with a String, Integer, Boolean, and Float
 
empty = []
#An empty array
```

every item in an array is in a numbered position starting with 0 at the first position. 

You can access the i'th position of an array by putting the index into square brackets after the arrays name. 

if `numbers = [1,2,3,4]` then `numbers[0] = 1 and numbers[1] = 2`

###### Array Methods

`each`method is used to iterate over arrays (and hashes). This method allows each element in an array to be iterated. 



### Hashes

a **hash** is a collection of key-value pairs. The hash is denoted by { } braces. Each value is assigned a key using a hash rocket (`=>`). Calling the hash followed by a key name within brackets grabs the value associated with that key.

A **hash** can be created by assigning a variable equal to `Hash.new` which generates a new, empty, hash.

``` profile = {
profile = {
  "name" => "Magnus",
  "profession" => "chess player"
  "ranking" => 1,
  "grandmaster?" => true
}
 
# "name", "profession", "ranking", and "grandmaster?" are the keys. "Magnus", "chess player", 1 and true are the values.
 
puts profile["name"] # => Magnus
```

values can be added to hashes using bracket notation.
`profile["beaten"] = "everybody"`

Similarly, you can access values in a hash using bracket notation. After the hash name, type the key in square brackets in order to access the value.
`profile["name"] # => "Magnus"`

A **hash** can also be created using symbols.

``` my_progress = {
my_progress = {
  :program => "Codecademy",
  :language => "Ruby",
  :enthusiastic? => true 
}
#Key symbols and their values can be defined with a =>, also known as a hash rocket.
 
my_progress = {
  program: "Codecademy",
  language: "Ruby",
  enthusiastic?: true 
}
#Key symbols and their values can also be defined with the colon (:) at the end of the symbol followed by its value.
```

`.select` can be used to grab specific values that meet certain criteria. 

``` olympic_trials = {
olympic_trials = {
  Sally: 9.58,
  John: 9.69,
  Bob: 14.91
}
 
olympic_trials.select { |name, time| time <  10.05 }
#The example above returns {:Sally=>9.58, :John=>9.69} since Sally and John are the only keys whose values meet the time < 10.05 criteria.
```

`.each_key` can be used to iterate over only the keys

`.each_value` can be used to iterate over only the values



### Sorting

`<=>` the combined comparison operator (spaceship operator) is used to compare two objects. It returns `0` if the first operand equals the second, `1`if the first is greater than the second, and `-1`if the second is greater than the first. 

``` puts "Keanu" <=> "Adrianna" # The first letters of each word are compared in ASCII order and since "K" comes after "A", 1 is printed.
puts "Keanu" <=> "Adrianna" # The first letters of each word are compared in ASCII order and since "K" comes after "A", 1 is printed.
 
puts 1 <=> 2 # -1
 
puts 3 <=> 3 # 0
 
#<=> can also be used inside of a block and to sort values in descending order:
my_array = [3, 0, 8, 7, 1, 6, 5, 9, 4]
my_array.sort! { |first_num, second_num| second_num <=> first_num }
print my_array
#Output => [9, 8, 7, 6, 5, 4, 3, 1, 0]
```

