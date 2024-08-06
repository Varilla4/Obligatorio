Pasos para la ejecución de los playbooks

Crear un usuario ansible para instalar la aplicación:
sudo useradd ansible

Instalar ansible:
Sudo dnf install Python-pip 
Pip install pipx 
Pipx ensurepath 
Pipx install ansible-core

Generar claves pública/privada:
ssh-keygen -t ed25519 -C "usuario@correo.com"

Copiar la clave pública a los servidores remotos:
ssh-copy-id usuario@servidor_remoto





Ejecutar playbook tomcat-todo.yaml:
ansible-playbook -i inventary/host playbooks/tomcat-todo.yaml --ask-become-pass


Ejecutar playbook basemariadb.yaml:
ansible-playbook -i inventary/host playbooks/basemariadb.yaml --ask-become-pass




 
