# Git-Cheat-Sheet <!-- omit in toc -->

<img src="https://repository-images.githubusercontent.com/621217226/205e99a2-827c-457d-b27c-1fa84f28e8a5" alt="" style="width:100%;"/>

# Table of Contents <!-- omit in toc -->

- [Glossary](#glossary)
- [Introduction](#introduction)
- [Create a Repository](#create-a-repository)
- [Configure tooling](#configure-tooling)
- [Branches](#branches)
- [Make changes](#make-changes)
- [Redo commits](#redo-commits)
- [The .gitignore file](#the-gitignore-file)
- [Synchronize changes](#synchronize-changes)
  - [Maintainers](#maintainers)
  - [Contributing](#contributing)
  - [License](#license)
  - [Contact](#contact)
- [References](#references)

# Glossary

**git**: an open source, distributed version-control system  
**GitHub**: a platform for hosting and collaborating on Git repositories  
**commit**: a Git object, a snapshot of your entire repository compressed into a SHA  
**branch**: a lightweight movable pointer to a commit  
**clone**: a local version of a repository, including all commits and branches  
**remote**: a common repository on GitHub that all team members use to exchange their changes  
**fork**: a copy of a repository on GitHub owned by a different user  
**pull request**: a place to compare and discuss the differences introduced on a branch with reviews, comments, integrated tests, and more  
**HEAD**: representing your current working directory, the HEAD pointer can be moved to different branches, tags, or commits when using git switch

# Introduction

A summary of useful git commands and other git functions

<p align="right">
	<a href="#top" style="font-size:2rem;color:#aac5c0;">▲</a>
</p>

# Create a Repository

1. In the command line, navigate to the root directory of your project.

2. Initialize the local directory as a Git repository.

```bash
# git init -b [<main-branch-name>]
# Example:
git init -b master
```

3. Stage and commit all the files in your project.

```bash
# git add <files-to-add>
# git commit -m [<commit-message>]
# Example (add all files):
git add . && git commit -m "initial commit"
```

4. To create a repository for your project on GitHub, use the `gh repo create` subcommand. When prompted, select Push an existing local repository to GitHub and enter the desired name for your repository. If you want your project to belong to an organization instead of your user account, specify the organization name and project name with `organization-name/project-name`.

5. Follow the interactive prompts. To add the remote and push the repository, confirm yes when asked to add the remote and push the commits to the current branch.

6. Alternatively, to skip all the prompts, supply the path to the repository with the `--source` flag and pass a visibility flag (`--public`, `--private`, or `--internal`). For example, `gh repo create --source=. --public`. Specify a remote with the `--remote` flag. To push your commits, pass the `--push` flag.

```bash
# gh repo create [<name>] [flags]

# create a repository interactively
gh repo create

# create a new remote repository and clone it locally
gh repo create my-project --public --clone

# create a remote repository from the current directory
gh repo create my-project --private --source=. --remote=upstream
```

<p align="right">
	<a href="#top" style="font-size:2rem;color:#aac5c0;">▲</a>
</p>

# Configure tooling

Configure user information for all local repositories

```bash
git config --global user.name "[name]"
```

Sets the name you want attached to your commit transactions

```bash
$ git config --global user.email "[email address]"
```

Sets the email you want attached to your commit transactions

```bash
$ git config --global color.ui auto
```

Enables helpful colorization of command line output

<p align="right">
	<a href="#top" style="font-size:2rem;color:#aac5c0;">▲</a>
</p>

# Branches

Branches are an important part of working with Git. Any commits you make will be made on the branch you’re currently “checked out” to. Use git status to see which branch that is.

```bash
git branch [branch-name]
```

Creates a new branch

```bash
git switch -c [branch-name]
```

Switches to the specified branch and updates the working directory

```bash
git merge [branch]
```

Combines the specified branch’s history into the current branch. This is usually done in pull requests, but is an important Git operation.

```bash
git branch -d [branch-name]
```

Deletes the specified branch

<p align="right">
	<a href="#top" style="font-size:2rem;color:#aac5c0;">▲</a>
</p>

# Make changes

Browse and inspect the evolution of project files

```bash
git log
```

Lists version history for the current branch

```bash
git log --follow [file]
```

Lists version history for a file, beyond renames (works only for a single file)

```bash
git diff [first-branch]...[second-branch]
```

Shows content differences between two branches

```bash
git show [commit]
```

Outputs metadata and content changes of the specified commit

```bash
git add [file]
```

Snapshots the file in preparation for versioning

```bash
git commit -m "[descriptive message]"
```

Records file snapshots permanently in version history

<p align="right">
	<a href="#top" style="font-size:2rem;color:#aac5c0;">▲</a>
</p>

# Redo commits

Erase mistakes and craft replacement history

```bash
git reset [commit]
```

Undoes all commits after [commit], preserving changes locally

```bash
git reset --hard [commit]
```

Discards all history and changes back to the specified commit

> CAUTION! Changing history can have nasty side effects.

<p align="right">
	<a href="#top" style="font-size:2rem;color:#aac5c0;">▲</a>
</p>

# The .gitignore file

Sometimes it may be a good idea to exclude files from being tracked with Git. This is typically done in a special file named `.gitignore`. You can find helpful templates for `.gitignore` files at github.com/github/gitignore.

<p align="right">
	<a href="#top" style="font-size:2rem;color:#aac5c0;">▲</a>
</p>

# Synchronize changes

Synchronize your local repository with the remote repository on GitHub.com

```bash
git fetch
```

Downloads all history from the remote tracking branches

```bash
git merge
```

Combines remote tracking branches into current local branch

```bash
git push
```

Uploads all local branch commits to GitHub

```bash
git pull
```

Updates your current local working branch with all new commits from the corresponding remote branch on GitHub. git pull is a combination of git fetch and git merge

<p align="right">
	<a href="#top" style="font-size:2rem;color:#aac5c0;">▲</a>
</p>

## Maintainers

[To be filled with maintainers' information]

<p align="right">
	<a href="#top" style="font-size:2rem;color:#aac5c0;">▲</a>
</p>

## Contributing

Contributions to the Git-Hooks project are welcome. If you would like to contribute, please contact [@Cusatelli](https://github.com/Cusatelli) for more information.

<p align="right">
	<a href="#top" style="font-size:2rem;color:#aac5c0;">▲</a>
</p>

## License

No License.

<p align="right">
	<a href="#top" style="font-size:2rem;color:#aac5c0;">▲</a>
</p>

## Contact

For any inquiries or questions, please contact Cusatelli at [github.cusatelli@gmail.com](mailto:github.cusatelli@gmail.com).

<p align="right">
	<a href="#top" style="font-size:2rem;color:#aac5c0;">▲</a>
</p>

# References

1. [Github Cheat Sheet](https://training.github.com/downloads/github-git-cheat-sheet/)

<p align="right">
	<a href="#top" style="font-size:2rem;color:#aac5c0;">▲</a>
</p>
