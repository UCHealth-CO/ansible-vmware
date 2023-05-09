# Dependencies

## Install Ansible
The example below is for RHEL/CentOS 8

```
sudo dnf -y install python3-pip
sudo pip3 install --upgrade pip
pip3 install ansible --user
```

## Clone Repo
```
git clone https://github.com/Sapphire-Health/ansible-vmware.git
cd ansible-vmware
```

## Install Dependencies
```
dnf install rhel-system-roles
ansible-galaxy collection install -r collections/requirements.yml
pip3.9 install pyVmomi
pip3.9 install requests
```

## Set environment variables
In Ansible Tower these values are configured using a "VMware vCenter" credential resource.

```
export VMWARE_HOST=vcenterhostname.fqdn.com
export VMWARE_USER=domain\\username
export VMWARE_PASSWORD=password
```

Optionally prompt for username and password so the values won't be saved in bash history

```
IFS= read -p 'Username: ' -r VMWARE_USER
IFS= read -s -p 'Password: ' -r VMWARE_PASSWORD
export VMWARE_USER
export VMWARE_PASSWORD
```

## List all VMs on ESXi hosts using dynamic inventory
```
ansible-playbook vminfo.yml
```
