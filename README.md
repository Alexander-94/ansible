# Ansible configs for Hetzner

apt install ansible-core  
ansible --version  
ansible localhost -m ping  

ansible-playbook -i hosts.txt docker_playbook.yml
