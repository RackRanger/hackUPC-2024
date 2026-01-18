## Install deps

ansible-galaxy role install -r requirements.yml

ansible-playbook -i inventory.ini playbook.yml --tags common --limit oracle

Make sure you have the lastest version of docker_compose_v2 module

ansible-galaxy collection install community.docker --force
