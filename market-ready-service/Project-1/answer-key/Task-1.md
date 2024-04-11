### TASK 1

For moving to `Documents` directory:

```cd Documents```

For adding two new folders:

```mkdir git-folder ansible-folder```

Installing `git` and `cmatrix`

```apt install git cmatrix -y```

For moving to `git-folder` and initializing `git` repository:

```mv git-folder && git init```

For adding five empty files and two hidden files:

```touch file1 file2 file3 file4 file5 .hidden1 .hidden2```

For adding these changes to the tracking area and committing these changes:

```git add . && git commit -m "added new files"```

For checking the status of the git repository and logs:

```git log```

For adding content use `nano` editor and open files one by one and add content:

```nano <file-name>```

For committing changes made of only one file:

```git add <file-name> && git commit -m "modified two files and excluding one from commit"```

For printing the number of users in the system:

```cat /etc/passwd | wc -l```

> Here the first command's (`cat /etc/passwd`) output is being used as an input to `wc -l` which is used for counting the number of lines.

For creating a new branch and naming it `new-branch`:

```git branch new-branch```

For entering that branch and making changes with commits:

```git checkout new-branch```

```git add . && git commit -m "modified files and committed changes on new-branch"```

For moving back to the `main` branch creating another new branch:

```git checkout main```

```git branch another-new-branch```

Again, make some changes using `nano` editor and commit those changes in new branch:

```nano <file-name>```

```git add <file-name> && git commit -m "commit message"```

For Creating a remote git repository on `Github` you would first have to create a github account and then create an repository in it.

After creating the repository, add it the local repository using the below command:

```git remote add origin <link>```

To list all the remote repositories present in local repository:

```git remote -v```

Pushing changes to the remote repository requires either a `ssh-key` configuration or authentication through `personal access token`.

Once you are done with the above configuration:

```git push origin <main-branch-name>```

> NOTE: All these commands were executed inside `git-folder` directory





