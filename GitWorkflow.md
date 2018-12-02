# Contribute to the project
Patches are the best way to provide a bug fix or to propose enhancements to the project.

## Setup your Environment
#### Install the Software
Before working, setup a friendly environment installing Git

#### Configure Git
Set up your user information with your real name and a working email address:
```sh
$ git config --global user.name "Your Name"
$ git config --global user.email you@example.com
```
If you are new to Git, you are highly recommended to read the excellent and free [ProGit](https://git-scm.com/book) book.

If your IDE creates configuration files inside the project's directory, you can use global .gitignore file (for all projects) or .git/info/exclude file (per project) to ignore them.

#### Get the Project Source Code
 Clone your repository locally (this will create a directory with the same name of the project)

```sh
$ git clone git@gitlab.com:USERNAME/PROJECT.git
```

## Work on your Patch
#### Choose the right Branch
Before working, you must determine on which branch you need to work. Most of the time you will need to add a new feature or fix a bug work. For this reason you will need to work on `develop` branch by creating a new topic branch.

#### Create a Topic Branch
Each time you want to work on a patch for a bug or on an enhancement, create a topic branch:
```sh
$ git checkout -b BRANCH_NAME develop
```

IMPORTANT: Use a descriptive name for your branch (PRJ_XXX where PRJ is an already defined abbreviation of the project name and XXX is the ticket number, is a good convention).

The above checkout commands automatically switch the code to the newly created branch (check the branch you are working on with `git branch`).

#### Work on your Patch
Work on the code as much as you want and commit as much as you want; but keep in mind the following:
- Read about the project conventions and follow the coding standards
- Add unit tests to prove that the bug is fixed or that the new feature actually works
- Do atomic and logically separate commits
- Write good commit messages (see the tip below)

IMPORTANT: A good commit message is composed of a summary (the first line), optionally followed by a blank line and a more detailed description. The summary should start with the Component you are working on in square brackets ([COMPONENT_NAME]). Use a verb (fixed ..., added ..., ...) to start the summary and don't add a period at the end.

#### Prepare your Patch for Submission
A review of all the changes must be done before submitting you work.

## Submit your Patch
Whenever you feel that your work is ready for submission, follow the following steps.

#### Rebase your Patch
Before submitting your patch, update your branch (needed if it takes you a while to finish your changes):
```sh
$ git checkout develop
$ git pull
$ git checkout BRANCH_NAME
$ git rebase develop
```
When doing the rebase command, you might have to fix merge conflicts. git status will show you the unmerged files. Resolve all the conflicts, then continue the rebase:
```sh
$ git add ... # add resolved files
$ git rebase --continue
```
Check that all tests still pass and push your branch remotely:
```sh
$ git push --force origin BRANCH_NAME
```

#### Make a Pull Request
You can now make a pull request on the PROJECT_NAME repository.

To ease the core team work, always include the modified components in your pull request message.
The default pull request description contains a table which you must fill in with the appropriate answers. This ensures that contributions may be reviewed without needless feedback loops and that your contributions can be included into the project as quickly as possible.

If the code is not finished yet because you don't have time to finish it or because you want early feedback on your work, add a `WIP` tag in front on your pull request title.

In the pull request description, give as much details as possible about your changes (don't hesitate to give code examples to illustrate your points). If your pull request is about adding a new feature or modifying an existing one, explain the rationale for the changes. The pull request description helps the code review and it serves as a reference when the code is merged (the pull request description and all its associated comments are part of the merge commit message).

In addition to this "code" pull request, you must also send a pull request to the documentation repository to update the documentation when appropriate.

#### Rework your Patch
Based on the feedback on the pull request, you might need to rework your patch. Before re-submitting the patch, rebase with upstream/develop, don't merge; and force the push to the origin:

```sh
$ git rebase -f upstream/develop
$ git push --force origin BRANCH_NAME
```

IMPORTANT: When doing a `push --force`, always specify the branch name explicitly to avoid messing other branches in the repo (`--force` tells Git that you really want to mess with things so do it carefully).
