
#Pasos para la ejecución de los playbooks, válidos para servidores GNU/Linux

#Crear un usuario ansible para instalar la aplicación:
sudo useradd ansible

#Instalar ansible y complementos necesarios, en este orden:

sudo dnf install Python-pip (requiere permisos de usuario root)
pip install pipx 
pipx ensurepath 
pipx install ansible-core
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
Agregando el grupo o host sobre el que se va a ejecutar el playbook

#Colecciones requeridas para playbook new_tomcat.yaml:
ansible-galaxy collection install ansible.posix (requerida para firewalld)

#Colecciones requeridas para playbook new_mariadb.yaml:
ansible-galaxy collection install community.mysql (requerida para trabajar con la base de datos) 
ansible-galaxy collection install community.general (requerida para firewall ufw)

#Ejecutar playbook new_tomcat.yaml:
ansible-playbook -i inventary/host playbooks/new_tomcat.yaml --ask-become-pass

#Ejecutar playbook new_mariadb.yaml:
ansible-playbook -i inventary/host playbooks/new_mariadb.yaml --ask-become-pass




 
