# lotof.cloud.image.dev

## Setup Guide

This guide will help you install Ansible, configure your inventory file, and run the playbook to set up your environment.

### Prerequisites

- A VM with SSH access.
- Ansible installed locally.
- SSH private key to access the VM.

### Step 1: Install Ansible

First, ensure that Ansible is installed on your local machine. If it's not already installed, you can install it using:

```bash
# On Ubuntu or Debian
sudo apt update && sudo apt install ansible -y

# On CentOS or RHEL
sudo yum install epel-release -y
sudo yum install ansible -y

# On macOS using Homebrew
brew install ansible
```

### Step 2: Create an Inventory File

Create an inventory file to define the target VM for Ansible:

```bash
echo '[my_vm]
VM_ADDRESS ansible_user=VM_USER ansible_ssh_private_key_file=~/.ssh/path/to/cert' > inventory
```

- Replace `VM_ADDRESS` with the IP address or hostname of your VM.
- Replace `VM_USER` with the SSH username.
- Replace `~/.ssh/path/to/cert` with the path to your SSH private key.

### Step 3: Run the Playbook

Once Ansible is installed and your inventory file is set up, run the playbook to configure your environment:

```bash
ansible-playbook -i inventory setup.yml
```

This will execute the playbook on the specified VM, installing and configuring the necessary components.

### Additional Information

- Ensure that your VM allows SSH connections and that your firewall is configured accordingly.
- The playbook is designed to handle typical setup tasks, including Docker installation and user permissions configuration.
