# notes-hi

A template repository for building a docs site from markdown docs/notes.

powered by MkDocs.

fast guide:

1. fork this repo and rename yours.
2. run!

Using command-line:

1. create new repo at github.com with name 'new-repo';
2. use bash:
   ```bash
   # clone notes-hi as a template
   git clone https://github.com/hedzr/notes-hi.git temp-dir
   cd temp-dir
   git push git@github.com:yourname/new-repo.git +master:master
   
   # in the working directory of your new-repo
   cd ..
   git clone git@github.com:yourname/new-repo.git
   cd new-repo

   # ./build.sh prepare_gh_pages_branch
   git checkout --orphan gh-pages
   rm -rf * .gitignore docs site 2>/dev/null
   touch README.md && git add README.md && git commit -m 'initial gh-pages commit' && git push origin gh-pages
   git checkout master && \
   git branch -D gh-pages && \
   git subtree add --prefix=site origin gh-pages
   
   #rm -rf site 2>/dev/null
   #git subtree add --prefix=site origin gh-pages
   ```
3. 


