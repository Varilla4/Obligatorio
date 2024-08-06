
#Pasos para la ejecución de los playbooks

#Crear un usuario ansible para instalar la aplicación:
sudo useradd ansible

#Instalar ansible:
Sudo dnf install Python-pip 
Pip install pipx 
Pipx ensurepath 
Pipx install ansible-core
pipx inject ansible-core argcomplete
pipx inject ansible-core ansible-lint
activate-global-python-argcomple --user

#Generar claves pública/privada:
ssh-keygen -t ed25519 -C "usuario@correo.com"

#Copiar la clave pública a los servidores remotos:
ssh-copy-id usuario@servidor_remoto

#Descargar el repositorio desde:
https://github.com/Varilla4/Obligatorio

#Editar el archivo host que se encuentra dentro de inventary (inventary/host)
agregando el grupo o host sobre el que se va a ejecutar el playbook

#Colecciones requeridas para playbook tomcat-todo.yaml:
ansible-galaxy collection install ansible.posix (requerida para firewalld)

#Colecciones requeridas para playbook basemariadb.yaml:
ansible-galaxy collection install community.mysql (requerida para trabajar con la base de datos) 
ansible-galaxy collection install community.general (requerida para firewall ufw)

#Ejecutar playbook tomcat-todo.yaml:
ansible-playbook -i inventary/host playbooks/tomcat-todo.yaml --ask-become-pass

#Ejecutar playbook basemariadb.yaml:
ansible-playbook -i inventary/host playbooks/basemariadb.yaml --ask-become-pass




 
