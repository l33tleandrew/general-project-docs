Commit Message
==============

Goals and General Information in commit messages
------------------------------------------------
* Provide better information when browsing the Git history
* Describe why a change is being made.
* Provide information about what effects the patch has
* Do not assume the reviewer understands what the original problem was.
* Do not assume the code is self-evident/self-documenting.
* Provide a reference to the ticket number
* Any line of the commit message cannot be longer 72 characters! This allows the message to be easier to read on github as well as in various git tools.
* use imperative, present tense: “change” not “changed” nor “changes”
* no dot (.) at the end of each line

Format of the commit message
----------------------------
```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```



### Subject line
Subject line contains succinct description of the change. A properly formed git commit subject line should always be able to complete the following sentence:

If applied, this commit will *\<your subject line here\>*

#### Allowed `<type>`
* feat (feature)
* fix (bug fix)
* docs (documentation)
* style (formatting, missing semi colons, …)
* refactor
* test (when adding missing tests)
* chore (maintain)

#### Allowed `<scope>`
Scope could be anything specifying place of the commit change. For example a component name, a file name, a module, a process etc...

#### `<subject>` text
* describe the change
* capitalize the first character

### Message body
* explain what and why you have done something. In most cases, you can leave out details about how a change has been made
* capitalize the first character
* use one line to describe just one change

### Message footer
#### Referencing issues

Closed tickets should be listed on a separate line in the footer prefixed with "Closes" keyword like this:
```
Closes #234
```

Examples
--------

```
docs(guide): Update docs from Google Docs

Fix indentation
Add punctation

Closes #351
```
