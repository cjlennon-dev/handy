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
  
  ## Naming things
  
It is often said that it is more important to be consistant in the way you name things than to be 'right'.  Naming things is largely a matter of convention.  I use the below naming convention:

- Folder names, file names, Lambda function names and urls are named as lowercase-with-hypen.  So `my-folder-name`, `my-file-name.js`, `/check-user-auth`
- In code use camelCase.  So `let myModule = require('my-module.js')`.  Simply camelCase all words, so `htmlPage` not `HTMLPage` `myApi` not `myAPI` and so on.
- Name commands e.g. npm scripts as lower-case-with-hyphen.   Its one less key-stroke than the underscore
- Name environment variables as UPPERCASE_WITH_UNDERSCORE.  Mainly because its just the convention
- Name configuration values (e.g. AWS IAM Users, CloudFormation stacks, API Gateway resources etc) as lowercase-with-hypen.  So `my-iam-user`, `my-cloudformation-stack` etc.  If the field does not allow hypens use underscores, and if underscores are not allowed used MixedCase

- For database tables (including Nosql databases such as AWS DynamoDB) and table field names use MixedCase.  So `Contacts`, `OrderLines` tables, `Id`, `FirstName` field names etc.  Use plurals for table names, so `Sessions` rather than `Session`, `OrderLines` over `OrderLine` and so on


- For everything else (and there is a lot else :-) )  use camelCase.  In the 'everything else' bucket would be JSON field names, HTML form fields, YAML fields etc


