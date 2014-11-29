# Coding Guidelines

## Overview

This document's purpose is to define how we write and maintain C#.


### Tabs

We use spaces not tabs.  4 spaces = 1 tab

### Bracing

Open braces start on the line following the statement that begins the block.


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
