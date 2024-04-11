### Project Content:

1. Create two ubuntu nodes on AWS and `ssh` into one of them.

Go to the `Documents` directory and add two new folders with the names given below:

  * git-folder
  * ansible-folder

Now, Install `git` and `apache2`.

After that go to the first folder and initialize `git` on it and add five empty files and two hidden file. Give them any random name.

Add and commit the newly added files with a message "added new files"

Check the status of the git repository and check the logs.

Add any desirable content to two of the 5 files. Add one of the changes and commit it with a message "modified two files and excluding one file from commit".

Now, using command line, print the number of users in the system.

After that create a branch in the git repository and name it "new-branch"

Enter that branch and add content to other files and commit that change with a message - "modified files and committed changed on new-branch"

Move back to the main branch and create a new branch with a name "another-new-branch"

Move to this branch and make some changes to the file and commit those changes.

Create a `git` repository on your `Github` Account and add that to the local repository `git-folder` as a remote repository with a name `remote-repo`

Push main branch to the remote repository.

2. Print the logged in user and move to it's `home` directory and clone a remote repository using the given link:

https://github.com/l3002/nu-tech-P1.git

Now, install `python3`. Make sure you update your `apt` repository before installing them.

Install `ansible` using it's documentation.

Try to check your connectivity with the other node created in "Task 1". Do `ssh` related configuration for `ansible`.

Create an inventory in the second folder (`ansible-folder`) with the other node.

Create two more nodes on `AWS` and configure them as well for ansible.

Add these servers to "new_servers" inventory groups.

Ping all the servers in the inventory for connectivity check.

Write a simple playbook for ping the servers in new_servers group and run the following command in them:

```echo Hello World!!```

Run this playbook and observe the output.

3. After that initialize `git` for `ansible-folder` as well. 

Commit all the changes made to the folder using separate commits.

Add a new Github repository for ansible-folder and push the main branch to it.

Modify the playbook to work on all the servers. Commit those changes as well and push them.

Create a new playbook with the name `ignored-playbook` and configure `git` in such a way that it ignores this playbook.

4. Go to the cloned repository and unzip the file added in it. 

After that restart the below services:

- ufw
- apache2


Now, disable the `apache2` services.

Go to the unzipped folder and configure the inventory with nodes created above.

Moreover, the modify the playbook inside it to reboot the systems in the inventory and run that playbook.

Add the commits to the repository and push the main branch to remote repository.

