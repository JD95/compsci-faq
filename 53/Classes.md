# Classes

## What is a Class?

A class adds a new type to the program. Generally, when breaking down a problem, the various "nouns" are isolated and turned into user defined types and the "verbs" are made to be functions associated with those types. They are usually combinations of basic types like ints or bools which help represent real world values.

For example, the combination of two integers can represent coordinates. A string and a number could be an address with a zip code. Etc.

The functions associated with classes are usually called "methods" and are different from normal functions. Methods have access to the values which are defined by the class and associated with an object (defined below).

### An example class in C++
```cpp
class Coord {
  int x; // Some ints
  int y; 

 public:

 // Given some Coord, increment it's y
 void goUp(){
   y += 1;
 }

 // Given some Coord, increment it's x
 void goLeft(){
   x -= 1;
 }

 // extract the value of x
 int getX() { return x; }

 // change the value of x
 void setX(int value) { x = value; }

 int getY() { return y; }

 void setY(int value) { y = value; }

};
```

For an explanation of what the "public:" line does, see "What is an Object" below.

## What is an Object?

Like there are many values which are ints or doubles, user defined types (classes) can also have many independent values. Typically, a specific version of a class is called an object. 

```cpp
Coord point;
```

Objects contain the values which are defined by it's class. So a Coord object would have two ints. Note that the programmer only has access to those values which are marked as "public". Typically, classes are defined so an object's methods will be public, but it's _member values_ are private. This prevents programmers from accidentally changes values when they don't mean to, or to otherwise restrict what kinds of changes are made to these values.

```cpp
int xCoord = point.getX();
int yCoord = point.getY();
```

Remember that a class can also define functions which are associated with the objects. Also note that every object can have different values from eachother. Although they all share the same class, they exist independently of eachother. Just like how setting one int doesn't change the value of all the others, changing the value of an object only affects that object.

```cpp
Coord a;
Coord b;

a.setY(0);
b.setY(0);

a.goUp();

cout << a.y << "\n"; // prints "1"
cout << b.y << "\n"; // prints "0"
```


## What is a Constructor?

Constructors are ways to create objects of a class with specific starting values. Typically these are used to either save the programmer some time by allowing for all the object's values to be defined at the same time, or they allow for an object to be created with default values.

Constructors are just functions with the same name as the class. If it takes no inputs, then it is a _default constructor_.

### An Example of a Class with Several Constructors
```cpp
class Coord {
  int x; // Some ints
  int y; 

public:

  // default constructor
  Coord() : x(0), y(0) {}

  // Typical constructor
  Coord(int i, int j) : x(i), y(j) {}

};
```
