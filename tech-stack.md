# Coding Guidelines

## Overview

This document's purpose is to define the normal techologies we use.   Its not an exclusive list but it is the list the team is confortable with maintaining.  Its also not always the stack of choice.  Every new product should be evaulated against the current stack and a decision should be made if it meets the domain needs of what is being built


### UI

#### MV** Framework  = AngularJS

When it comes to a goto framework for creating SPAs that need a tight integration with an API (AngularJS)[https://angularjs.org/] is our framework of choice.  Preferred modules are below:

*  Built in ng-<modules>... touch, animate, santize, etc
*  Routing:  (Angular UI Router)[https://github.com/angular-ui/ui-router]
*  Bootstrap: (Angular UI Bootstrap)[https://github.com/angular-ui/bootstrap]
*  (ng-grid)[https://github.com/angular-ui/ng-grid] - flexible table layout for json based data.
* ? more

#### SASS

We use SASS to generate CSS.  

#### Friendly JS Frameworks

* MomentJS
* Underscore JS
* lodash


#### Build Automation Tools

We use (gulpjs)[http://gulpjs.com] as our frontend build system.  It handles all things related to front end development.  From jshting, minifcation, uglification, unit-testing, ziping, etc.


#### UI Testing

We currently use Karma & Jasmine as our testing frameworks.  


### API

Our APIs currently consist .NET Web API , Entity Framework, & SQL Server.


#### C# Testing

We currently use NUnit & Fluent assertions to test .NET code.
