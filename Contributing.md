# Contribution to Noise Studio projects

> Keep in mind that we are all people beings. We may not understand each other, we may not have the time, but let's try to get along to create great things.

You can contribute to open source projects with issues and PRs. Simply filing issues for problems you encounter is a great way to contribute. Contributing implementations is greatly appreciated.

## Reporting issues
We always welcome bug reports, API proposals and overall feedback. Here are a few tips on how you can make reporting your issue as effective as possible.

### Identify where to report
We have many projects, it is important to report issue in good repository. You should check whether this applies to e.g. NoiseEngine (Core) or NoiseEngine.Cli. But when you do not know, do not panic, always you know use [less formal communication forms](#i-just-want-to-ask-a-simple-question).

### Finding existing issues
Before filling a new issue, please search issues list to check if it already exists.

If you do find an existing issue, please include your own feedback in the discussion. Do consider upvoting (👍 reaction) the original post, as this helps us prioritize popular issues in our backlog.

### Writing a good bug report
Good bug reports make it easier for maintainers to veryfi the underlying problem. The better a bug report, the faster the problem should be resolved. Ideally, a bug report should contain the following information:
* A high-level description of the problem.
* A minimal reproduction, i.e., the smallest size of code/configuration required to reproduce the wrong behavior.
* A description of the expected behavior, constracted with the actual behavior observed.
* Information on the environment: OS, CPU, RAM, GPU etc.
* Additional information, e.g. is it a regression from previous version? Are there any known workarounds?

When ready to submit a bug report, please use the `Bug report` issue template when it exists.

### Why are minimal reproductions important?
A reproduction lets maintainers verify the presence of a bug, and diagnose the issue using a debugger. A minimal reproduction is the smallest possible console application demonstrating that bug. Minimal reproductions are generally preferable since they:

1. Focus debugging efforts on a simple code snippet,
2. Ensure that the problem is not caused by unrelated dependencies/configuration,
3. Avoid the need to share production codebases.

### Are minimal reproductions required?
No, the most important thing is to report the problem. But when issue do not have a minimal reproduction, a patch will take longer.

Other people can also add a reproduction to yours issue.

### How to create a minimal reproduction?
The best way to create a minimal reproduction is gradually removing code and dependencies from a reproducing app, until the problem no longer occurs. A good minimal reproduction:

1. Excludes all unnecessary types, methods, code blocks, source files, dependencies and project configurations.
2. Contains documentation or code comments illustrating expected vs actual behavior.
3. If possible, avoids performing any unneeded IO or system calls.

### Writing a good API proposal
Currently we do not have any good, guidelines on how to submit an API proporsal. But you should describe your idea well, submit adventages, and disadventages. And better do not start implementation before accepting the proporsal.

## Contribution changes
Project maintainers will merge changes that improve the project significantly. 

### DOs and DON'Ts
Please do:
* **DO** follow our coding style and [GIT workflow](/GitWorkflow.md) (you find it in this repository).
* **DO** include tests when adding a new features. When fixing bugs, start with adding a test that highlights how the current behavior is broken.
* **DO** keep the discussions focused. When a new or related topic comes up it is often better to create new issue than to side track the discussion.
* **DO** clearly state on an issue that you are going to take on implementing it.
* **DO** blog and tweet (or whatever) about your contributions, frequently!

Please do not:
* **DON'T** surprise us with big pull requests. Instead, file an issue and start a discussion so we can agree on a direction before you invest a large amount of time.
* **DON'T** submit PRs that alter licensing related files or headers. If you believe there's a problem with them, file an issue and we will be happy to discuss it.
* **DON'T** add API additions without filing an issue and discussing with us first. See [API proporsals](#writing-a-good-api-proposal).

### Breaking changes
Make breaking changes only to accepted API proporsals, after you discuss with us about how new API should looks.

### I create PR, what now?
Now your PR must be checked from one of us maintainers, after it will be approved and CI/CD tests passed (if exists) mainteiner merge this to target branch.

But remember to discuss with maintainer and pay attention to they change requests. If you do not pleased of they request, please ping one of our developers.

### My PR is old, but I do not want to fix it, what I should do?
Propably we just close this PR, but when it is very good, it have chance to be taken by one of our developers to fix it.

## I just want to ask a simple question
It is not in every case necessary to create a new issue or discussion on GitHub. Then you can use forms of communication less formal like e.g. Discord.

**Ok, where I can find invite to Discord community?**
<br>
Currently we do not have one offical community for all things related with Noise Studio. But if offical community exists for some project, you can find a invite in it README.  
