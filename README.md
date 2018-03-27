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
  
It is often said that it is more important to be consistant in the way you name things than to be 'right'.  Naming things is largely a matter of convention.  I personally use the below naming conventions:

- Folder names, file names, Lambda function names and urls are named as lowercase-with-hypen.  So `my-folder-name`, `my-file-name.js`, `/check-user-auth`.  The only exceptions are the `LICENSE` file and `README.md`

- If it makes sense to join two words together then do so.  Its one less hypen.  So `lowercase-with-hypen` over `lower-case-with-hyphen`.  But only if the joined word makes sense: don't do `my-reallygood-component`.  This is a subtle one, don't sweat it too much

- In code use camelCase.  So `let myModule = require('my-module.js')`.  Simply camelCase all words, so `htmlPage` not `HTMLPage` `myApi` not `myAPI` and so on.

- Name commands e.g. npm scripts as lower-case-with-hyphen.   Its one less key-stroke than the underscore

- Name environment variables as UPPERCASE_WITH_UNDERSCORE.  Mainly because its just the convention

- Name configuration values (e.g. AWS IAM Users, CloudFormation stacks, API Gateway resources etc) as lowercase-with-hypen.  So `my-iam-user`, `my-cloudformation-stack` etc.  The reason for this is that Voyzu resources are tightly coupled with their component - which will be named using lowercase-with-hypen.  If the field does not allow hypens use underscores, and if underscores are not allowed use MixedCase

- Database naming:
    - For DynamoDB Database table names use lowercase-with-hyphen .  So `contacts`, `order-lines` tables.  This is because Voyzu resources are tightly coupled with their component - which will be named using lowercase-with-hypen
    - For MySql table names use lowercase_with_underscore.  This is because MySQL doesn't like hypens in its table names
    - Use plurals for table names, so `sessions` rather than `session`, `order-lines` over `order-line` and so on
    - For table field names use MixedCase e.g. `Id`, `FirstName` field names etc.  

- For everything else (and there is a lot else :-) )  use MixedCase.  In the 'everything else' bucket would be JSON field names, HTML form fields, YAML fields etc.  There is no real reason for this, it just keeps things consistant, and having no non alpha-numeric characters means it wil always be allowed


