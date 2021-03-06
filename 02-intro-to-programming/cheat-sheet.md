# Cheat Sheet

- [Array Cheat Sheet](#array-cheat-sheet)
- [Enumerable Cheat Sheet](#enumerable-cheat-sheet)
- [Hash Cheat Sheet](#hash-cheat-sheet)


## Array Cheat Sheet

### Manipulation

```rb
# add element(s) to the end using push
people = ["Tommy", "Bex"]
p people.push("Maurice", "Abby")      # prints ["Tommy", "Bex", "Maurice", "Abby"]
p people                              # prints ["Tommy", "Bex", "Maurice", "Abby"]

# remove the last element using pop
people = ["Tommy", "Bex"]
p people.pop()                        # prints "Bex"
p people                              # prints ["Tommy"]

# add elements(s) to the front using unshift
people = ["Tommy", "Bex"]
p people.unshift("Oscar", "Matthias") # prints ["Oscar", "Matthias", "Tommy", "Bex"]
p people                              # prints ["Oscar", "Matthias", "Tommy", "Bex"]  

# remove the first element using shift
people = ["Tommy", "Bex"]
p people.shift()                      # prints "Tommy"
p people                              # prints ["Bex"]
```

### Checking Existence

```rb
# check if an element exists in an array using include?
people = ["Tommy", "Bex", "Abby", "Maurice"]
p people.include?("Abby")   # prints true
p people.include?("Mashu")  # prints false

# find the index of an element in an array using index
people = ["Tommy", "Bex", "Abby", "Maurice"]
p people.index("Abby")      # prints 2
p people.index("Maurice")   # prints 3
p people.index("Oscar")     # prints nil
p people.index("Danny")     # prints nil
```

### String <> Array

```rb
# convert a string into an array using split
sentence = "Hey Programmers! What's up."
p sentence.split(" ")      # prints ["Hey", "Programmers!", "What's", "up."]
p sentence.split("a")      # prints ["Hey Progr", "mmers! Wh", "t's up."]
p sentence.split("gram")   # prints ["Hey Pro", "mers! What's up."]
p sentence                 # prints "Hey Programmers! What's up."

# convert an array into a string using join
words = ["Rubies", "are", "red"]
p words.join(" ")          # prints "Rubies are red"
p words.join("-")          # prints "Rubies-are-red"
p words.join("HI")         # prints "RubiesHIareHIred"
p words                    # prints ["Rubies", "are", "red"]
```


## Enumerable Cheat Sheet

### Array Enumerable Methods

```rb
people = ["Candace", "Jon", "Jose"]

# iterate over elements of an array using each
people.each { |person| puts person } # prints
# Candace
# Jon
# Jose

# iterate over elements of an array with index using each_with_index
people.each_with_index do |person, i|
  puts person
  puts i
  puts "-----"
end # prints
# Candace
# 0
# -----
# Jon
# 1
# -----
# Jose
# 2
# -----
```

### String Enumerable methods

```rb
greeting = "hello"

# iterate over characters of a string using each_char
greeting.each_char { |char| puts char } # prints
# h
# e
# l
# l
# o

# iterate over characters of a string with index using each_char.with_index
greeting.each_char.with_index do |char, i|
  puts char
  puts i
  puts "---"
end # prints
# h
# 0
# ---
# e
# 1
# ---
# l
# 2
# ---
# l
# 3
# ---
# o
# 4
# ---
```

### Other

```rb
# repeat a block using times
3.times do
  puts "hi"
end # prints
# hi
# hi
# hi

# specify a range of numbers using (start..end) or (start...end)

# including end
(2..6).each {|n| puts n} # prints
# 2
# 3
# 4
# 5
# 6

# excluding end
(2...6).each {|n| puts n} # prints
# 2
# 3
# 4
# 5
```


## Hash Cheat Sheet

### Access

```rb
hash = { "name" => "App Academy", "color" => "red" }

p hash["color"]  # prints "red"
p hash["age"]    # prints nil

k = "color"
p hash[k]        # prints "red"

hash["age"] = 5
p hash           # prints {"name"=>"App Academy", "color"=>"red", "age"=>5}
```

### Checking Existence

```rb
hash = { "name" => "App Academy", "color" => "red" }

p hash.has_key?("name")             # prints true
p hash.has_key?("age")              # prints false
p hash.has_key?("red")              # prints false

p hash.has_value?("App Academy")    # prints true
p hash.has_value?(20)               # prints false
p hash.has_value?("color")          # prints false
```

### Hash Enumerable Methods

```rb
hash = { "name" => "App Academy", "color" => "red" }

hash.each { |key, val| p key + ', ' + val} # prints
# "name, App Academy"
# "color, red"

hash.each_key { |key| p key } # prints
# "name"
# "color"

hash.each_value { |val| p val } # prints
# "App Academy"
# "red"
```

### Hash.new

```rb
plain_hash = { }
plain_hash["city"] = "SF"
p plain_hash["city"]    # prints "SF"
p plain_hash["country"] # prints nil

hash_with_default = Hash.new("???")
hash_with_default["city"] = "NYC"
p hash_with_default["city"]    # prints "NYC"
p hash_with_default["country"] # prints "???"
```
