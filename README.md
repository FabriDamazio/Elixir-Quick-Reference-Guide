# Elixir-Quick-Reference-Guide
Elixir through code samples

## Table of Contents
* [Hello World](#hello-world)
* [Basic Data Types](#basic-data-types)
* [Arithmetic Operations](#arithmetic-operations)
* [Boolean Operators](#boolean-operators)
* [Comparison Operators](#comparison-operators)
* [Collections](#collections)

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

