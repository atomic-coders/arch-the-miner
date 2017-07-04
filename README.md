Node:
1. Install [Antergos](antergos.com)
2. Enable ssh service:
```
  sudo systemctl enable sshd.service && sudo systemctl start sshd.service
```
3. Enabled passwordless sudo for your user:
```
	sudo visudo
```
	Add the following line:
```
	Defaults:your_username      !authenticate
```

Provisioner:
1. Put hosts into `/usr/local/etc/ansible/hosts`.

2. Execute Ansible Playbook:
```
  ansible-playbook playbook.yml --ask-become-pass --extra-vars "pool_host=eth-eu1.nanopool.org:9999 pool_user=0xd32AbCebFFc1F436Ffa19fA01a7504c15a1B0923.black/maciej.rosiek@gmail.com"
```


