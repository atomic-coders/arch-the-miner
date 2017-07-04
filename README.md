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
1. Use `inventory.example` file as a template for your `inventory`.

2. Execute Ansible Playbook:
```
  ansible-playbook playbook.yml -i inventory --extra-vars "pool_host=eth-eu1.nanopool.org:9999 pool_user=0xd32AbCebFFc1F436Ffa19fA01a7504c15a1B0923.black/maciej.rosiek@gmail.com"
```

Monitoring endpoints:
	- Prometheus: `[prometheus]/`
	- Alerts: `[prometheus]/alert`
	- Grafana: `[prometheus]/grafana`
