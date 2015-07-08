# Coding Guidelines

## Overview

This document's purpose is to define how we write and maintain C#.


### Tabs

We use spaces not tabs.  4 spaces = 1 tab

### Bracing

Open braces start on the line following the statement that begins the block.
```C#
if (x == 1)
{
  //code here
}
```

When you have one line of code inside an if or loop, do not use braces like below
```C#
-- Incorrect
if (x == 1)
{
  someLineOfCode();
}

for (var a in collection)
{
  someLineOfCode();
}

-- Suggested
if (x == 1)
  someLineOfCode();
  
for (var a in collection)
  someLineOfCode();
```

### Use of var & explicit declariations

Use 'var' when type is explicitly declared in the same line or implied by another declaration.

```C#
  --Incorrect
  Dictionary<int, SomeObjectThatIWant> dictionary = new Dictionary<int, SomeObjectThatIWant>();
  
  --Suggested
  var dictionary = new Dictionary<int, SomeObjectThatIWant>();
  
```

An example of another declaration with in your context suggesting the type:

```C#
  --Incorrect
  List<Customer> customers = new List<Customer>();
  
  foreach (Customer customer in customers)
  {
  
  }
  
  --Suggested
   var customers = new List<Customer>();
  
  foreach (var customer in customers)
  {
  
  }
  
```

### Capitalization & Naming

.NET uses uppercase naming for Classes & Properties.  camelCase is used for member variables, parameters, and local variables.



### Directory & Files

Directory structure should match namespace.  One type per file (inner classes are allowed)


### When using Newtonsoft Serializier.

We turn off serializing nulls ```NullValueHandling = NullValueHanding.Ignore```



### Web API

We return native types and let the serializer handle it.  


We do not allow unhandled exceptions to be thrown to client.  The allowed list of exceptions are below:

```//@TODO create this list. (Unauthorized, ValueError, e.g.)```


### Entity Framework

We do not use lazy loading.  We use ```Include()``` to pull in related entities.  We do not keep contexts open longer than needed.


