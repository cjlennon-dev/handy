# handy
some handy git etc commands

## Git

### To store credentials within a repo.  

This stores the creds locally, un-encrypted within the repo folder.  Its not ideal but it is handy when you want to use https and you can't seem to get the credentials on the repo remembered by windows / your code editor

`git remote set-url origin https://user:password@github.com/username/MyRepo.git`

see https://stackoverflow.com/questions/6565357/git-push-requires-username-and-password
