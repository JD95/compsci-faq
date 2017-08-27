# Pointers

## What are pointers?

## Short Story
- Pointers are [references](51/references.md) which can change what value they refer to

## Long Story

Imagine that variables are like boxes in a wearhouse. You (the programmer) are like the manager of the warehouse. The workers don't like it when you go onto the warehouse floor and mess with their boxes so here are the rules: you cannot directly touch the boxes, you can only instruct your workers to make new boxes or put new things into existing boxes, but you aren't trusted to do much else.

In this analogy, functions would be like other rooms that do some work. If some other room needs access to some stuff in the warehouse, you are kinda restricted because the workers refuse to let anyone else mess with their boxes. So normally, if another room wants to work with some stuff, you can tell the workers to make a new box with the same stuff in the box and send it over. This means that no matter what the other room does with the box, nothing happens to the original. The workers are happy.

If for some reason, the other room *needs* to mess with a very specific box, then the workers are willing to compromise. You can give the other room the location of the box in question, but it's the workers that will go and change it. In this way, the other room doesn't directly work with the box, they merely have a way to reference the box when they need it.

If the other room decides they aren't actually dealing with the box that they want, they can change the location they give the workers to talk about another box.
