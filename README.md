# handy
some handy git etc commands

## Npm

Check for package updades. Various packages do this, the one I like is npm-check.  Install it from npm and run `npm-check -u`

## Git

### To store credentials within a repo.  

This stores the creds locally, un-encrypted within the repo folder (in .git/config).  Its not ideal but it is handy when you want to use https and you can't seem to get the credentials on the repo remembered by windows / your code editor

`git remote set-url origin https://user:password@github.com/username/MyRepo.git`

see https://stackoverflow.com/questions/6565357/git-push-requires-username-and-password

### Delete all commit history in github

Its not something you'd want to do lightly, but if you have been playing around and you don't want to expose your vague ramblings in your code to the world, you can delete your commit history (still of course keeping your actual code).  To do this follow the instructions in:
https://stackoverflow.com/questions/13716658/how-to-delete-all-commit-history-in-github

Or if you do this kind of thing a lot and you are using nodejs you could even create a script like:
````json
"scripts": {
    "git-nuke-history" : "git checkout --orphan latest_branch & git add -A & git commit -am \"nuke\" & git branch -D master &  git branch -m master & git push -f origin master"
  },
  ````


