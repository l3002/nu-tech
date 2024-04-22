### Task 1

For creating the new directory in `home` directory:

`mkdir ~/docker-ansible`

>There are a lot of other ways to create new directory in `home` directory of the current user. You can use any them.

To enter into the `docker-ansible` and creating an `ansible` inventory:

`cd docker-ansible`
`nano inventory.ini`

Once you have opened the file using `nano` editor add the following contents to the file:

```
<ip-address>
```

>This is the IP Address of the other node.

Using the Ansible's community Documentation from the below link, Install `ansible`:

[Ansible Installation Guide](https://docs.ansible.com/ansible/latest/installation_guide/index.html)

>It is very important as if you will install it using apt package manager, it might not install ansible-config command and you might have to add a configuration file manually.

For creating a playbook inside the folder, use `nano`:

`nano playbook.yaml`

Once the `nano` editor is open, add the following contents to the file and save it:

```
---
- name: Update apt and install docker
  hosts: all

  tasks:
  - name: Updating apt repository
    ansible.builtin.apt:
      update_cache: yes
    become: yes
    become_method: sudo

  - name: Installing Docker
    ansible.builtin.apt:
      name: docker.io
      state: present
    become: yes
    become_method: sudo
```

>NOTE: Here, we have used sudo for privilege escalation even though it has been deprecated. This has been done for simplicity. This kind of privilege escalation is discourages. In production, we might use ansible-vault or Environment variable references for privilege escalation.

For initializing `git` repository and committing the changes made:

```
git init
git add .
git commit -m "<commit-message>"
```

To check the logs for `git` repository:

`git log`

For creating a new branch and checking out into it:

`git checkout -b new-branch`

For adding new tasks the playbook, use `nano` to open `playbook.yaml` and then add the following contents below `tasks`:

```
- name: Removing containerd
  ansible.builtin.apt:
    name: containerd
    state: absent
  become: yes
  become_method: sudo

- name: Re-Installing containerd
  ansible.builtin.apt:
    name: cotainerd
    state: present
  become: yes
  become_method: sudo
```

For committing newly added changes:

```
git add .
git commit -m "<commit-message>"
```

Now checkout to the main branch using the following commit:

`git checkout main`

To add a handler to the playbook, Add the below line to the end of the file and modify the `Re-Installing containerd` task in `new-branch`:

```
handlers:
  - name: Restart containerd
    ansible.builtin.service:
      name: containerd
      state: Restart
```

```
- name: Re-Installing containerd
  ansible.builtin.apt:
    name: cotainerd
    state: present
  become: yes
  become_method: sudo
  notify:
    - Restart containerd
```

To commit changes:

```
git add .
git commit -m "<commit-message>"
```

Rebasing `new-branch` with respect to `main`:

`git rebase new-branch main`

In this part you, might get an error due to the merge conflict, This is due to the changes made to the same file.

You can resolve this conflict using the `git-mergetool` and `vimdiff`

Install both the utilities:

`apt install git-mergetool vimdiff -y`

Once done, Use `git-mergetool` 

It will open up a window for resolving merge commit, fix the parts and the save the file.

After this run the following command to continue, rebasing:

`git rebase --continue`

This will prompt an window for editing the commit message.

Do that and continue.

For merging the `new-branch` to `main`:

```
git checkout main
git merge new-branch
```

