# Elixir-Quick-Reference-Guide
Elixir through code samples

## Table of Contents
* [Hello World](#hello-world)
* [Basic Data Types](#basic-data-types)
* [Arithmetic Operations](#arithmetic-operations)
* [Boolean Operators](#boolean-operators)
* [Comparison Operators](#comparison-operators)
* [Collections](#collections)
* [Enum](#enum)

---

### Hello World
```elixir
IO.puts "Hello World"
```
[back to top](#table-of-contents)

---

### Basic Data Types
```elixir
255       # integer
0b0110    # binary
0o644     # octal
0x1F      # hexadecimal
3.14      # float
1.0e-10   # float (support e for exponencial values)
true      # boolean (are also atoms, is_atom(true) -> true)
:foo      # atom (constant whose name is its value)
"Hello"   # string
```
[back to top](#table-of-contents)

---

### Arithmetic Operations
```elixir
2+2       # addition
3-1       # subtraction
3*5       # multiplication
10/3      # division (always return a float)
div(10,2) # integer division
rem(10,3) # modulo (division remainder)
```
[back to top](#table-of-contents)

---

### Boolean Operators
```elixir
# Operatos that accepts arguments of any type
false || true   # Or operator
false && true   # And operator
!true           # Non-strict not

# Operators whose first argument must be a boolean
true and 10     # And operator
true or false   # Or operator
not false       # Not operator
```
[back to top](#table-of-contents)

---

### Comparison Operators
```elixir
2>1     # Greater than
1<2     # Less than
1<=2    # Less than or equal to
1>=2    # Greater than or equal to
1==1    # Equal 
1===1   # Strict equal (for integer and floats)
1!=1    # Not equal
1!==1   # Strict not equal (for integer and floats)

# Any two types can be compared. The sort order:
# number < atom < reference < function < port < pid < tuple < map < list < bitstring
```
[back to top](#table-of-contents)

---

### Collections
```elixir
list = [1.01, :test, "Hello"]         # list
["World" | list]                      # list prepending
list ++ "World"                       # list appending
[1,2] ++ [3,4]                        # list concatenation
[:foo, "bar"] -- ["bar"]              # list subtraction

# Head (first element) and Tail (rest of the list)
[head | tail] = [:foo, :bar, :boo]    # head = :foo and tail = [:bar, :boo]
hd [:foo, :bar, :boo]                 # hd function returns the head (:foo)
tl [:foo, :bar, :boo]                 # hd function returns the tail ([:bar, :boo])

{1.01, :test, "Hello"}                # tuple
[{:foo, "bar"}, {:hello, "world"}]    # keyword lists
map = %{:foo => "foo", :bar => "bar"} # maps
```
[back to top](#table-of-contents)

---

### Enum
```elixir
Enum.all?(["foo", "bar"], fn(s) -> String.length(s) > 1 end)    # the entire collection must evaluate to true otherwise false will be returned
Enum.any?(["foo", "bar"], fn(s) -> String.length(s) == 1 end)   # return true if at least one item evaluates to true
Enum.chunk_every([1, 2, 3, 4, 5, 6], 2)                         # break a collection up into smaller groups
Enum.chunk_by(["a", "b", "ab"], fn(x) -> String.length(x) end)  # group a collection based on a condition
Enum.map_every([1, 2, 3, 4], 2, fn x -> x + 1000 end)           # apply function every x items
Enum.each(["one", "two", "three"], fn(s) -> IO.puts(s) end)     # iterate over a collection without producing a new value
Enum.map([0, 1, 2, 3], fn(x) -> x - 1 end)                      # apply a function to each item and produce a new collection
Enum.min([1, 2, 3, -1])                                         # finds the minimal value
Enum.max([1, 2, 3, -1])                                         # finds the maximal value
Enum.filter([1, 2, 3, 4], fn(x) -> rem(x, 2) == 0 end)          # filter based on a condition
Enum.reduce([1, 2, 3], fn(x, acc) -> x + acc end)               # distill a collection down into a single value
Enum.sort([5, 6, 1, 3, -1, 4])                                  # sorting a collection using Erlang term comparison
Enum.sort([2, 3, 1], :desc)                                     # sorting a collection descending
Enum.sort([2, 3, 1], :asc)                                      # sorting a collection ascending
Enum.uniq([1, 2, 3, 2, 1, 1, 1, 1, 1])                          # remove duplicates
Enum.uniq_by([%{x: 1, y: 1}, %{x: 2, y: 1}], fn z -> z.y end)   # remove duplicates based on a condition
```
[back to top](#table-of-contents)

