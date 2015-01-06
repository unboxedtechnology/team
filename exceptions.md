# Coding Guidelines

## Overview

This document's purpose is to define the general guidelines to follow when dealing with exceptions.

## General Principles

### What is an exceptional condition?

The rule we follow is if the method can not accomplish what the name implies its an exceptional condition.  

### What is the exception message for?

Exception message should be friendly enough for the end user to know what is going on.  Do not use it programtically. So I should not be string parsing an exception mesasge to "figure out" what went wrong.  (See: Picking the right exception)

### Picking the right exception

Use system exceptions when they make sense.  E.g. `ArgumentNullException` , `UnauthorizedAccessException` and make sure you understand the exception class.  Sometimes the exception that is thrown has additional information that can be use to react to.  e.g. [`ArgumentNullException`](http://msdn.microsoft.com/en-us/library/k8a0dfcy.aspx)  has a constructor that allows for you to inform the catcher which paramater was null.  

When creating your own exception you can always customize the exception class itself and return extra information to the catcher.  Remember to keep it layer specific, because the caller is the one that should be handling this exception.  Only provide infomration that is useful to the exception.  DO your best to not *enable* developers to use progamatic exceptions by providing them with excessive information.  

### Don't programatically use exceptions for control flow.  
### Don't knowingly allow exceptions to get thrown.  

Use the [tester-dooer pattern](http://msdn.microsoft.com/en-us/library/ms229009%28v=vs.110%29.aspx) .

Don't progamatically use exceptions or purposily write dangerous code that will throw exceptions.  If for some reason you do do this, *always* document it.  [Joel](http://www.joelonsoftware.com/articles/Wrong.html) also ellaborates on why it's bad to throw exceptions programatically.

e.g. (bad)

    var nick = _context.UserFavorites.First().UserName 
    try{
    
    }catch(NullReferenceException){
      //do something
    }

better:

    var nick = _context.UserFavorites.FirstOrDefault();
    if(nick ==null){
      //do something
    }


Code that throws unhandled exceptions is code that is bugy.  Those cases where exceptions get thrown are "missed / untested" paths through code.  Good / Simple Design allows developers to understand all paths through there application.


### Don't catch the unkown.  Don't catch what you can't handle.

"It's almost always wrong to catch, or throw  `System.Excecption`".  All exceptions stem from `System.Exeption` so when you catch it you have no clue what actually went wrong.
This opens the door for allowing the system to continue in an unstable state, or even can cause bugs to be hidden. In general do your best to allow exceptions to bubble up so we can triage them as they surface.

In the event you catch an exception and you can not handle it make sure you ["rethrow" versus throw](http://stackoverflow.com/questions/22623/throwing-exceptions-best-practices) the same exceptions;

    //Correct
    try{
    }catch(Exception e){
      throw;  //this is correct it will rethrow the same exception
    }


    //BAD
    try{
    }catch(Exception e){
      throw e;  //this will reset the stack trace...
    }

If you catch an exception and rethrow a different type make sure you pass the original exception to the new exception.  This allows for the stacktrace (innerexception) to not get lost.

    //good
    try{
    }catch(Exception e){
      throw new CustomBusinessLogicException("New message", e); 
    }
    
### Document the exceptions you will be throwing from your API.  
### Treat exceptions as part of your APIcontract.  
### Only catch documented exceptions.

    /// <summary>
    /// Abbey is this the right format? 
    /// </summary>
    /// <param name="source">Source</param>
    /// <exception cref="ArgumentNullException">
    /// Thrown if Source is null</exception>
    /// <returns>A object</returns>

It's important to document the exceptions that can be thrown from your API.  
If you are going to throw them you should give a developer the oppertunity to catch them.  And the converse is also true only catch the exeptions that the API declares it throws.  We do this for many reasons the simplist jusfication is that you should not have intimate knowledge of the APIs you call.  
Their documentation should be all you know and use.  

E.g.  If I am in the a Web API controller I should not be catching DataAccess exceptions that are being thrown 2 layers down.  The controller should be kept free of "implementation logic" of the data access layer.  It would be completely appropriate to catch a "Business Layer" exception.


### Global Error Handlers

Don't forget about "dont catch what you can't handle" but in the event you do add a global error handling to your application keep in mind these things:

1.  If you put it at the "Global" / Application layer the app will have to hault inorder to handle the exceptions.  So if your server is throwing exceptions at a high rate performance will be effected.
2.  If possible put your exception handling logic at the BaseController level so that when the exception bubles up / out you can catch it and gracefuly handle it.
3.  It's ok to shieled the exception (e.g. catch it and convert it to json in an error handler).  But make sure you do enough to support maintainablity.  This means log it to a database, spam someone, just make sure in production when it happens it's noisy.  *Remember, we do our best to not allow unhandled exceptions bubble up through our app.*

###  Usage vs Execution error.

A usage error is when a developer  / user incorrectly calls a public api.  Best example of this is the ArgumentNullException.  When we are coding we should never purposfuly allow the `ArgumentNullException` to get thrown.  We should use the tester-doer pattern and prevent it.

An execution error is something that can not be prevented by better code.  They are generally system related failures like IO issues (connection / access).  

Why do I mention this ? Two reasons 

1. Avoid creating new exceptions for UsageError. There is usually and exception in the `System` namespace that will accomplish your goal.  
2. Be careful catching Execution exceptions because often there is not much more you can do besides provide a friendly message to the end user.
3. 

### If you are not handling the exception do not use the    

### Resources

