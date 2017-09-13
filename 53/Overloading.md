# Overloading

Definition: The means by which the same function name can be used to do different things, typically with the same return type.

Recall that a function is a mapping of some input values to some output values. For example, a function "add1" might take two integers and produce an integer.

A simple way to notate this is 

> add : (int, int) Ë int

So what if we wanted a version of add1 that worked for doubles? Naively we could simply make another funciton that does the same thing, but changing the name and types.

> add_doubles : (double, double) Ë double

However, as we continue to find more version of the same function we'd want to use it becomes clumbersome to have to define a new name for every possible instance where we'd want to add two things.

> add\_int\_double : (int, double) Ë double

> add\_double\_int : (double, int) Ë double

> add_strings : (string, string) Ë string

It would be much simpler if we could just call "add" and let the compiler figure out which version we mean. This is infact a real feature of C++ called "overloading". There are two rulesets which apply to the two possible kinds of overloading you can do. 

The first kind is overloading a normal function like "add". In this case, we can define many functions with the same name so long as they all have the same return type. A good example of this would be a to_string funciton.

> to_string : int Ë string

> to_string : bool Ë string

> to_string : double Ë string

The second kind of overloading applies to functions with special names (operators). Operators are the common symbols like +, -, <<, =, etc which are reserved by C++ to be functions. You can overload operators in much the same way that you can normal functions, except that when overloading them, you must add "operator" infront of the symbol to prevent the compiler from freaking out.

```cpp
double operator+ (double x, bool y){
  ...
}
```

A good reference for the rules of operator overloading and useful examples can be found at [cppreference](http://en.cppreference.com/w/cpp/language/operators).
