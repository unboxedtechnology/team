# Coding Guidelines

## Overview

This document's purpose is to define how we use git.  Our familiar patterns and best practices


## Branching

We use short, but descriptive, lowercase branch names. Our standard branches are

master
dev (default)
test
uat


### Feature Branching / Bug Fixes

When we are feature branching use simple but descriptive names.  Use `-` to separate words.  Feature branches are designed to be short lived.  Once the changes have been integrated into the mainline they should be deleted.

e.g.

```git

  git checkout -b sync-api
  git checkout -b community-perf-fixes

```

## Tagging

Our tags are based on (Semantic Versioning)[  http://semver.org/].  

>Given a version number MAJOR.MINOR.PATCH, increment the:
>  MAJOR version when you make incompatible API changes,
>  MINOR version when you add functionality in a backwards-compatible manner, and
>  PATCH version when you make backwards-compatible bug fixes.
>  Additional labels for pre-release and build metadata are available as extensions to the MAJOR.MINOR.PATCH format.

We update our bower.json/package.json/web.config with this pattern.


TODO (Rick/Scott) explain the process that happens after we code freeze.  e.g. we need to increment the version at least once.

```git

   git tag 1.0.1
   git tag 1.0.2 (this means we had to do anther build on this date)


```
