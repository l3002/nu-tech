### Project Content:

1. Create two ubuntu nodes on AWS and `ssh` into one of them.

   Create a new directory in the `home` directory:

   * `docker-ansible`

   Move to `docker-ansible`, create an inventory inside it and add the newly created nodes to it.

   Install `ansible` using Ansible's documentation.

   After this, create a playbook inside the folder which updates the `apt` repository and installs `docker.io` package.

   Initialize the `git` repository and commit the changes made to the file.

   Once done, check the logs for git and checkout into a new branch.

   In the `new-branch`, add a new task to the playbook which re-installs `containerd` and commit the changes.

   In the main, branch add a new handler to the playbook which restarts the service `containerd` after re-installing `containerd` and commit the changes.

   Now, rebase the `new-branch` with respect to main and once done, check  the changes made to the playbook in `new-branch` branch.

   After that merge the `new-branch` to `main`.

2. Create a default config file for ansible and configure it to use privilege escalation for tasks which require it.

   Add a new user to the other node for `ansible` and configure `ssh` for connectivity.

   Check if the playbook created in step 1 is correct and then run it.

   Now, Create a new playbook for creating two containers in other node using image `l3002/sshd` and expose port number `22` of both the container with port `9000` and `9001` of the host respectively.

   Check if the playbook created is using the correct syntax and then run it and fix any failures.

   `ssh` into the other server from terminal and add new users to the containers created from playbook for `ansible`.

   Define a custom `hostname` for the other node, so that ansible control node is able to connect to it using this `hostname`

3. Add the containers created in the last step to the inventory using the hostname and add them in a group named `docker-ssh`

   Using Ad Hoc commands `ping` one of the containers.

   Create a new playbook which pings both the containers and run it.

4. Create a new Github repository and add it the repository initialized earlier.

   Change the commit message of the last commit and sign it off.

   After that using a `Personal Access Token`, push the all the commits to the remote repository.

