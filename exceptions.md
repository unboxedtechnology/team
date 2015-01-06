# Coding Guidelines

## Overview

This document's purpose is to define the general guidelines to follow when dealing with exceptions.

## General Principles

### What is an exceptional condition?

The rule we follow is if the method can not accomplish what the name implies its an exceptional condition.  

### Don't programatically use exceptions for control flow

### Don't catch the unkown

### Don't catch what you can't handle.
"It's almost always wrong to catch, or throw  `System.Excecption`".  All exceptions stem from `System.Exeption` so when you catch it you have no clue what actually went wrong.
This opens the door for allowing the system to continue in an unstable state, or even can cause bugs to be hidden. In general do your best to allow exceptions to bubble up so we can triage them as they surface.

### Document the exceptions you will be throwing from your API.  Only catch documented exceptions.

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

### Resources

