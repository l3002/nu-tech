### Task 2

For creating a default config file for ansible:

```
sudo su
ansible-config init --disabled -t all > /etc/ansible/ansible.cfg
```

This command will redirect the out of the command to the default ansible configuration file.

Once done, then as the super user, open the file `/etc/ansible/ansible.cfg` and modify the content such that the below values are identical to the corresponding lines in file:

```
remote_user=ansible-user
become=true
become_ask_pass=true
become_method=sudo
```

For adding a new user to the other node:

```
ssh <default-user>@<ip-address>

adduser ansible-user
```

For configuring `ssh` for ansible, run the following command from the ansible control node:

```
ssh-copy-id <ansible-user>@<ip-address>
```

To check if the has the correct syntax run the following command:

`ansible-playbook -i <inventory> <playbook-name> --syntax-check`

To check if the ansible-playbook is working correctly on remote machine:

`ansible-playbook -i <inventory> <playbook-name> --check`

To run the playbook on remote machine:

`ansible-playbook -i <inventory> <playbook-name>`


To Create a new playbook use `nano` editor and add the following contents to the file:

```
---
- name: Containers with Ansible
  hosts: all

  tasks:
    - name: Create Container 1
      ansible.builtin.docker_container:
        name: container-1
        image: l3002/sshd
        ports:
          - "9000:22"

    - name: Create Container 2
      ansible.builtin.docker_container:
        name: container-2
        image: l3002/sshd
        ports:
          - "9001:22"
```

To check and run the playbook refer to the previous commands and use it in this context.

For adding a new user to the containers:

```
ssh <ansible-user>@<ip-address>
sudo docker exec -it container-1 adduser ansible-user
sudo docker exec -it container-2 adduser ansible-user
```

Remember that you will also have to configure `ssh` for ansible on these two containers as well, You can do this using the following command:

```
ssh-copy-id -p 9000 ansible-user@<ip-address>
ssh-copy-id -p 9001 ansible-user@<ip-address>
```

> NOTE: These commands needs to be run from the control node

In Order to define a custom `hostname` for the other node locally in control node, You will have to modify `/etc/hosts` file and add a new entry to it, just like the below example:

```
<ip-address> <hostname>
```

This will bind the IP address provided to the hostname and the local DNS server will be able to resolve this node.
