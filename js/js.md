# Coding Guidelines

## Overview

This document's purpose is to define how we write and maintain javascript.

## File Structure

Lower case file names.  Bower to manage js.  Jshint & Minfiy your source (dont include maps in production).  

### Declare your variables...

All variables need to be declared. The most performant and reccomended way to do this is by declaring them all at the top of your block.  We do not use window based variables.  If we do we expect them to be referenced window.<variable name> .    Exceptions are when we are passing variables from razor to Angular.

### Capitalization

Class constructors are upper case.  Everything else is camel case.

```
function MyConstructor(){

}

var myInstance = new MyConstructor();

```

### Indentation

We use spaces.  If you use an ide set it to insert spaces for tabs.  Our default is 4. Feel free to debate with your project team, but stick with 2 or 4.

### Function Declarations

We prefer:

```
function test() {
    //indent me 4  
}
```

Over:

```
var test = function () {
  //indent me 4

}

```

When using anonymous functions we prefer to put spaces around the parens e.g.

this.doWork  = function () {
  //this gives more space to make sure we understand there is *no* name for this function
}


### Whitespace improves readability... too much causes readability issues.

When you are dealing with logic that is "logically related" dont be affraid you use white space to separate.

### Use single quotes.

### Wrap full files in a closure. e.g.


```
(function(){

    // my entire file goes here

})()
```
