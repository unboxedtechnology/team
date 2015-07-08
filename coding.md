# Coding Guidelines

## Overview

This document's purpose is to define the core principles we code by.  

## We commit to:

We as an Engineering team are committing to doing the following before marking features/  stories complete:
* Code Cleanup – Ensuring the code is free of commented out blocks of code, matches unboxed coding guidelines, and is well commented
* Documenting Technical Debt – if there were things that you could not get to because of constraints we will document them in L.P.
* Updating LP – Obviously we will need to update LP status to “Ready for Test” but also we will provide useful comments about the nature of the change, impacted areas, etc
* Bug free, or known issues documented and communicated
  * This communication belongs in the task or in the story itself
  * We will do one final gauntlet of tests before marking things as done

We are also committing to before starting a big feature / pattern:
* We will perform a design review with another member of the team.  The goal of this to to be able to get feedback on the design and be able to identify potential issues in advance

Lastly when a task / change is high risk:
* If a task that consist of new patterns, new application of technology, or any other high risk change we will seek out code reviews




## General Principles

### B.S Rule

We actively clean and fix code.  If we enter an area that needs some love we clean up as much as we can given time.  If we see things that violate our standards we fix them.  From naming, tabs vs spacing, jshint errors, duplicate code, etc.  Whatever the case we always try to fix the things we see and document those that we must ignore.


### Code review early and often

Why?

1. Enforce & Re-enforce team principles

2. Architectural changes. Its important to have someone look validate your design early and to challenge the solution.  We do this to help validate the design before its too late.  You don't have to always fix everything, but it's important that you at least acknowledge and accept any flaws in the design.

3. Teaching.  Code changes fast, and an excellent way to learn is through application & others.  Code reviews are an excellent time to learn something new, or learn a different way of doing or thinking.

### Responsibility

We make responsible decisions. We build software that businesses depend on so we need to be diligent with our designs & tools.  We want to stay on top of technology but we need to be mindful when adopting the new and shiny.  


We are small so we do no re-invent wheels.  We look to partner with well maintained open source technologies and when applicable we give back to the open source community.


### We produce clean code

We strive to write code that is simple and easy to consume.  By doing this it allows for us to document less.  We error on the side of brevity.  Our functions are atomic and mission oriented.  We comment when necessary and we avoid the superfluous.


### Principles we believe in:

1. (S.O.L.I.D)[http://en.wikipedia.org/wiki/SOLID_%28object-oriented_design%29]
2. (KISS)[http://en.wikipedia.org/wiki/KISS_principle]
3. (DRY)[http://en.wikipedia.org/wiki/Don%27t_repeat_yourself]
