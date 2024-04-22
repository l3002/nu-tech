### Task 3

For adding the containers to the inventory using `hostname`, add the following to the `inventory`:

```
[docker-ssh]
<hostname>
```


For pinging the first container use the following command:

```
ansible docker-ssh -i <inventory> -e "ansible_port=9000" -m ping
```

For pinging the second container use the following command:

```
ansible docker-ssh -i <inventory> -e "ansible_port=9001" -m ping
```
