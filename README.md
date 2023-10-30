# Invent Framework Documentation

This repository contains the documentation for the _Invent_ framework. The
documentation is hosted at
[https://invent-framework.github.io](https://invent-framework.github.io).

We use [MkDocs](https://www.mkdocs.org/) as a static site generator for
building and curating the documentation's website.

The rest of this README assumes you are familiar with core coding concepts such
as `git`, GitHub, repositories, the command line, Python and virtual
environments.

## Setup

First, fork this project in GitHub.

Next clone your forked repository, remembering to replace `<username>` with
your actual username on GitHub:

```sh
git@github.com:<username>/docs.git
```

Add this repository as upstream to your forked project. This will allow you to
pull in changes and updates into your own fork of the repository.

```sh
git remote add upstream git@github.com:invent-framework/docs.git
```

To grab the latest changes from our upstream project, while in your own `main`
repository:

```sh
git pull upstream main
```

Next, create a Python virtual environment in your usual way and, once
activated, install the dependencies from the `requiremets.txt` file in the root
of this repository:

```sh
pip install -r requirements.txt
```

Should you have the privileges to deploy the website, you should also clone
the `invent-framework` repository, used by GitHub pages to host our
documentation, into an adjacent directory:

```sh
git@github.com:invent-framework/invent-framework.git
```

The end result should look something like this:

```
docs/
  mkdocs.yml
  docs/
  ... etc ...
invent-framework/
  ... auto-generated assets ...
```

## Contribute

Unless you're making trivial changes (such as to correct speeling, or fixing
broken links), please raise an issue within this project on GitHub explaining
the change you propose to make. Doing so helps **avoid the situation where
folks invest time and effort into work that is ultimately rejected**.

We are a friendly bunch, so please reach out to us. We also expect folks who
contribute to our project to engage in the spirit described
[on being together](https://invent-framework.github.io/being_together/).

Should you wish to contribute a change ensure your forked repository is up to
date with our upstream repository and then create a new branch (replacing
`my-new-branch` with a meaningful name of your actual branch):

```sh
git checkout main  # switch to the main branch.
git pull upstream main  # pull changes from upstream.
git checkout -b my-new-branch  # create a new branch.
```

Edit the files you need to make your change, please write useful commit
messages and then push your branch to your fork of the repository on GitHub:

```sh
git add a_file.md
git add another_file.md
git commit -m "A meaningful commit message."
git push origin my-new-branch
```

Finally, visit you repository on GitHub and [create a pull request](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request) (PR).

Your PR will be reviewed, changes may be requested and, once in a fit state to
merge, will be included in the project! Congratulations and thank you very
much!

## Test

Assuming you have activated your virtual environment, installed the project
dependencies and are in the root of the repository, it is possible to see the
current state of the documentation on your local filesystem by typing:

```sh
mkdocs serve
```

Then point your browser to [http://127.0.0.1:8000/](http://127.0.0.1:8000/) to
view your local version.

**As you make changes to your local files these will automatically be detected
and updated by mkdocs.**

## Deploy

If you have the correct privileges, to deploy the main branch of the docs to 
GitHub pages ensure you have the correct adjacent `invent-framework` repository
as described in the [setup section](#setup).

Next, ensure you are in the root of the `invent-framework` repository and issue
the following command:

```sh
mkdocs gh-deploy --config-file ../docs/mkdocs.yml --remote-branch main
```

This may be automated in the future for when a PR is ever merged into `main`.
But for the time being, this process is simple enough.
