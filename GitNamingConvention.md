# Git - Naming Convention

## Branches
> Name of the branch should is as close as possible to the title of the corresponding task on e.g. Trello or issue.

Branches must be named using kebab-case e.g.:
```
different-terrain-version-blocks-matching
```

## Commits
> A one-sentence commit message cannot end with a punctuation mark, but a multi-sentence commit message must end with a punctuation mark.

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

## Workflow
* You cannot commit directly to production branches such as master. To make changes to the production branch, you create a `pull request`, which is then assessed and approved by another developer with the appropriate permissions.<br>
As a developer who is merging changes, you are responsible for resolving conflicts and are responsible for possible errors related to your changes.

* You cannot commit changes that contain changes unrelated to your task. For example, replacing the texture in the API development task.

* It is allowed to use commands such as `"git rebase"`, however, it is not allowed to overwrite commit dates.