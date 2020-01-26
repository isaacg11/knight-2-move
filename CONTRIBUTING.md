## Contributing
![](https://img.shields.io/static/v1?label=Node.js&message=^13.1.0&color=green) ![](https://img.shields.io/static/v1?label=NPM&message=^6.12.1&color=green) ![](https://img.shields.io/static/v1?label=React.js&message=^16.12.0&color=green)

First off, thank you for considering contributing to Knight2Move! 

### Getting Started
To get started, you will need to make sure you have NodeJS installed on your machine. If you don't have Node, you can install it by visiting https://nodejs.org/en/.

### Reporting Bugs & Adding New Features

If you've noticed a bug or have a feature request, it's
generally best if you get confirmation of your bug or approval for your feature
request this way before starting to code.

### Fork & create a branch

If this is something you think you can fix, then fork knight2move and create
a branch with a descriptive name.

A good branch name would be (where issue #99 is the ticket you're working on):

```
git checkout -b 99-add-new-feature
```

### Implement your fix or feature

At this point, you're ready to make your changes! 

### Add a changelog entry

If your PR includes user-observable changes, you'll be asked to add a changelog
entry following the existing changelog format.

The changelog format is the following:

* One line per PR describing your fix or enhancement.
* Entries end with a dot, followed by "[#pr-number] by [@github-username]".
* Entries are added under the "Unreleased" section at the top of the file, under
  the "Bug Fixes" or "Enhancements" subsection.
* References to github usernames and pull requests use [shortcut reference
  links].
* Your github username reference definition is included in the correct
  alphabetical position at the bottom of the file.

### Make a Pull Request

At this point, you should switch back to your master branch and make sure it's
up to date with knight2move's master branch:

```
git remote add upstream git@github.com:knight2move/knight2move.git
git checkout master
git pull upstream master
```

Then update your feature branch from your local copy of master, and push it!

```
git checkout 99-add-new-feature
git rebase master
git push --set-upstream origin 99-add-new-feature
```

Finally, go to GitHub and make a Pull Request!

### Keeping your Pull Request updated

If a maintainer asks you to "rebase" your PR, they're saying that a lot of code
has changed, and that you need to update your branch so it's easier to merge.

```sh
git checkout 99-add-new-feature
git pull --rebase upstream master
git push --force-with-lease 99-add-new-feature
```

