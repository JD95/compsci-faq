# Refactorings

Writing code is hard. Debugging it is ten times harder. It goes without saying that we should try to write simple and clear code whenever possible. Too often do code smells accumulate as projects go on and sometimes we need to refactor our code in order to regain sanity. In general, refactoring is the process of changing a program without altering the semantics of the code. 

All of the changes here merely change how the code looks rather than what it *does*.

### Pairs of Loops

Loops are very noisy code blocks and you should try to have as few of them in a function as possible. A common code smell a completely duplicated loops which only differ on the *inside* of the loop.

```java
if (condition) {
  for (int i = 0; i < n; i++) {
    doSomethingA();
  }
}
else {
  for (int i = 0; i < n; i++) {
    doSomethingB();
  }
}
```

Given that the shape of the loops are the same, we can pull the if statement *into* the loop and thus remove the duplicated loops.

```java
for (int i = 0; i < n; i++) {
  if(condition){
    doSomethingA();
  }
  else {
    doSomethingB();	
  }
 }
```

### Returning True or False

Most of the time, if statements inside of a function which calculates a boolean are redundant.

```java
Boolean condition(int x, int y) {
  if (x < y){
    return true;
  }
  else {
    return false;
  }
}
```

Notice that the return values of the if statement are exactly the same as the result of the if condition itself. If you find that x *is* less than y, then there is no need to return true as you *already* have calculated that result.

```java
Boolean condition(int x, int y) {
  return x < y;
}
```
