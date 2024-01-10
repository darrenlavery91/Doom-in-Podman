# Doom-in-Podman: Ansible Playbooks for Managing the Doom Game Container

This repository provides Ansible playbooks for seamless management of the Doom Game container using Podman.

## Usage:

### Install Ansible:

#### Linux (Red Hat):
```bash
sudo yum install -y ansible
```

#### Mac (via Brew):
```bash
brew install ansible
```

1. Create the directory in your user space:
   ```bash
   mkdir -p ~/ansible/
   cd ~/ansible
   ```

2. Create the `ansible.cfg` file:
   ```bash
   vim ansible.cfg
   ```
   Add the following configuration and save:
   ```ini
   [defaults]
   inventory=./inventory
   ```

3. Create the `inventory` file:
   ```bash
   vim inventory
   ```
   Add the following, replacing `your-local-ip` with your actual local IP:
   ```ini
   [localhost]
   your-local-ip ansible_connection=local
   ```
   Example:
   ```ini
   [localhost]
   192.168.101.214 ansible_connection=local
   ```

4. Run `ansible --version` to verify if the configuration file has been picked up.

### Install Podman:

#### Red Hat (RHEL):
```bash
sudo yum install -y podman
```

#### Mac (via Brew):
```bash
brew install podman
```

#### Silicon Macs (M1):
To start the Podman machine on Silicon Macs (M1), use the following command:
```bash
podman machine start
```

5. Run the Ansible playbook to start the Doom Game container:
   ```bash
   ansible-playbook your_playbook_file.yml
   ```

6. After successful execution, access the Doom Game through the provided URL.

7. Run the Ansible playbook to stop and remove the Doom Game container:
   ```bash
   ansible-playbook your_playbook_file.yml
   ```

## Note:

- Customize the playbooks according to your specific requirements.
- Ensure proper network configurations and permissions for successful execution.
- A big thank you to CallumHoughton18 for their contributions.
