### Task 4

Create a Github Repository using the `HTTPS` URL create an entry for remote repository in local repository created in Task 1, using the following command:

`git remote add <identifier> <HTTPS-URL>`

Once you have created that, To create a `Personal Access Token`:

```
# Click on the profile picture

Go to Settings > Developer Settings > Personal Access Token > Token (Classic)
```

And Create a token, which can be later used for authentication. 

Save this Token, somewhere (preferably as a Environment variable) and then to push the changes to remote repository:

`git push <identifier> <branch-name>`
