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

For Creating adding a task to `playbook-4.yaml` to `ping` both containers, modify the file to look something like this:

```
---
- name: Ping both containers
  hosts: com.worker1

  tasks:
    - name: Change ssh port to 9000
      set_fact:
        ansible_port: 9000
    - name: Pinging container-1
      ping:
    - name: Change ssh port to 9001
      set_fact:
        ansible_port: 9001
    - name: Pinging container-2
      ping:
```

In order to create a pull request, you must first create a branch and commit those changes to that branch:

```
git add playbook-4.yaml
git commit -m <commit-message>
```

Now, After this you need to push this branch to the remote repository, which is a fork of `l3002/ansbile-practice`:

```
git push origin <branch-name>
```
