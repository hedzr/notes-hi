# %REPOSITORY%

![CI](https://github.com/%REPOSITORY%/workflows/CI/badge.svg)

A template repository for building a docs site from markdown docs/notes.

powered by MkDocs.

## fast guide:

1. All you have to do is click the <kbd>Use this template</kbd> button upon this page.
2. run!

## Using command-line:

### new repo

1. clone notes-hi as a template
   ```bash
   # clone notes-hi as a template
   git clone https://github.com/hedzr/notes-hi.git new-repo
   cd new-repo
   git push git@github.com:yourname/new-repo.git +master:master
   ```
   
2. clone the `new-repo` to your working directory:
   ```bash
   # in the working directory of your new-repo
   cd ~/work
   git clone git@github.com:yourname/new-repo.git
   cd new-repo
   ```

3. publish as gh-pages:
   1. via `build.sh`:
   ```bash
   # ./build.sh prepare_gh_pages_branch
   git checkout --orphan gh-pages
   rm -rf * .gitignore docs site 2>/dev/null
   touch README.md && git add . && git commit -m 'initial gh-pages commit' && git push origin gh-pages
   git checkout master && \
   git branch -D gh-pages && \
   git subtree add --prefix=site origin gh-pages
   
   #rm -rf site 2>/dev/null
   #git subtree add --prefix=site origin gh-pages
   ```
   > If error occurs at `git subtree add ...`: `prefix 'site' already exists`, try this:
   > ```bash
   > git subtree split --rejoin --prefix=site origin gh-pages
   > ```
   2. via mkdocs gh-deploy
      ```bash
      mkdocs gh-deploy
      ```



