### TASK 2

To print logged in users:

```users```

For moving to the `home` directory:

```cd```

OR 

`cd ~`

For cloning any repository:

```git clone <link>```

For updating `apt` repository and installing `python3`:

```apt update && apt install python3```

For installing `ansible`:

```
sudo apt update 
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansiblesudo apt install ansible
```
For checking connectivity with other nodes created in "Task 1":

```ping <ip-address-hosts>```

To Configure `ssh` for `ansible`:

```
// On Worker Node
apt install openssh-server
systemctl enable --now openssh-server

// On Control Node
ssh-keygen
ssh-copy-id <user>@<ip-address>
```
Before creating the file:

```cd ansible-folder```

To create a functional inventory, using `nano` open a file named `inventory.ini` and add below content to it:


```
<ip-address-1>

[group-name-1]
<ip-address-2>
<ip-address-3>

[group-name-2]
<ip-address-1>
<ip-address-2>
```

For pinging all the servers in inventory:

```
ansible all -i inventory.ini -m ping

// Or 

ansible all -i inventory.ini -m ansible.builtin.ping

```

To create a playbook use `nano` and add the below contents to the playbook file:

```
---
- name:
  hosts: new-servers
  tasks:
    - name: Ping new-server hosts
      ansible.builtin.ping:
    - name: Print message
      ansible.builtin.command:
        cmd: echo "Hello World"
```


