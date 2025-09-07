Ansible Project Setup

1. Instance Setup
  Created two EC2 instances (Ansible server and target server).

  Updated both instances: sudo apt update
  
  Installed Ansible on both: sudo apt install ansible -y

3. SSH Key Configuration
   Generated public and private SSH keys on both instances using: ssh-keygen
   Copied the public key of Ansible server and added it to the ~/.ssh/authorized_keys of the target server.
   Verified connectivity by logging into the target server: ssh <target-server-private-ip>

4. Ansible Inventory Setup
   Created an /ansible directory on the Ansible server.
   Inside it, created an inventory file and added the target server’s private IP

5. Ad-Hoc Commands
   Ran an ad-hoc Ansible command to create a file on the target server: ansible all -i inventory -m file -a "path=/tmp/testfile state=touch"

6. Playbook
   Wrote a playbook to:
   Install Nginx on the target server.
   Start and enable the Nginx service.
