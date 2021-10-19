# Git - Naming Convention

## Branches
> Name of the branch should is as close as possible to the title of the corresponding task on e.g. Trello or issue.

Branches must be named using kebab-case e.g.:
```
different-terrain-version-blocks-matching
```

## Commits
Commits must be in the imperative present tense and they must be preceded by one of these words:
* `Add` - Create a capability e.g. feature, test, dependency.
* `Remove` - Remove a capability e.g. feature, test, dependency.
* `Fix` - Fix an issue e.g. bug, typo, accident, misstatement.
* `Bump` - Increase the version of something e.g. dependency.
* `Make` - Change the build process, or tooling, or infra.
* `Refactor` - A code change that must be just a refactoring.
* `Reformat` - Refactor of formatting, e.g. omit whitespace.
* `Optimize` - Refactor of performance, e.g. speed up code.
* `Document` - Refactor of documentation, e.g. help files.