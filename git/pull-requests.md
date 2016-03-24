# Pull Requests

## Overview

This document is designed to be an explanatory document on pull-requests.  It includes the why, when, and what.

### The PR Process
Why do a PR?  Good question.  The two most important use cases for PRs are to inform or to get approval.  Informs are a good way to say

>hey guys I just made this change and I want you to be aware of it.  Let me know if you have questions.

Alternatively:

>hey reviewers, I just implemented #1123.    Please take a look and make sure it's as you expected.  Once you approve i'll merge it in.

Good pull requests are designed to be more informative then interrogative.   Always understand why you are creating a PR.  Get to know your teams (roles & responsibilities)[./Roles and Responsibilities.md].  Generally by the time you get to that point you are creating a PR you should be either at the very beginning (working on getting design approval) or at the very end (code complete).  Never should you be creating a PR that has code that is complete and is just now getting technical design approval.  


### Before the Requests
Figure out the intent of your PR.  Is this an inform?  Are there any approvals needed?  If it's an inform let people know how you want feedback.  If it's an approval figure out who that is and make sure you set expectations for turn around time.   Let them know as soon as possible that something might be coming so they can plan accordingly.

### Preparing the Requests
Before you submit the request make sure your branch is ahead of whatever branch you are targeting merging. Clean up your commits and make them as succinct as possible.  That means *interactive* rebases to squash those incremental or WIP commits. If you have a commit that fixes a bug place the bug number in the commit.  Why? you might ask.  Well not all PRs have to be merged in.  Sometimes a subset of a PR might get approved, so if you organize your commits this makes that possible.  

Take some time and give a good description of your pull request.  Give details to people about the nature of the change, complexity, or level of risk.  Give reviewers direction.  Let them know the areas to focus on, or why you are including them.

### Reviewing a PR
I'm a reviewer what do I do ? Annoying answer is whatever the requester asked you to.  If you are not sure always ask, if you reviewed it and aren't sure place a comment and let people know what you reviewed.  Always keep an eye out for best practices, well documented code, and potential problem areas.  

What you should ignore? Subjective things. e.g. Did the person do it how you would ?  If not dont force them to do it your way, just make sure they understand potential issues with their design.

Create checklist items for things that need to be fixed.  Don't be afraid of "conditionally approving."  

> Hey Nick as long as you complete the checklist items you have my approval.

Conditional approvals will speed up the process because they wont require you to come back and review things that aren't mission critical.

### Finishing the Requests
 It's on you to get this process complete.  Nag, bribe, force your reviewer to complete it.  The person who is responsible for ensure the PR gets completed in a timely manner is *YOU.*  We dont like pull request that survive more than a day so dont be the guy that violates that principle.
