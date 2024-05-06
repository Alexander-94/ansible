# Ansible configs for Hetzner
1. SSH Putty login
2. apt install ansible-core
3. apt install git
5. Create an SSH key: ssh-keygen -t rsa -b 4096
6. Copy the content of the key file: cat ~/.ssh/id_rsa
7. Add the public key to the authorized_keys file: cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
8. Create GitHub’s Container Registry Token(PAT): https://github.com/settings/tokens/new?scopes=write:packages,read:packages,delete:packages
9. In GitHub Set Settings>Secrets and Variables>Actions>Repository secrets
   Set vars:
   
            SSH_PRIVATE_KEY: content of the private key file
   
            SSH_USER: user to access the server
   
            SSH_HOST: IP of your server
   
            WORK_DIR: path to the directory containing the docker-compose.yml file
   
            PAT: the personal access token to login to the registry
11. git clone https://github.com/Alexander-94/ansible.git
12. ansible-playbook -i hosts.txt docker_playbook.yml

For services port tuning, change docker-compose in service/service-name

# Other
apt install ansible-core  
ansible --version  
ansible localhost -i hosts.txt -m ping  
ansible-playbook -i hosts.txt docker_playbook.yml
