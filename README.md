Este repositorio contiene el inventario y los playbooks utilizados en el obligatorio de la materia **Administración de Servidores Linux**.

## Requisitos
- Ansible instalado en el bastión o máquina de control.
- Clave pública SSH copiada a los servidores.
- Archivo `inventory.ini` configurado con las direcciones IP correctas.

## Prueba del playbook de NFS en CentOS
En el bastión, ejecutar:
```bash
ansible-playbook -i inventory.ini nfs_setup.yml

Esto instalará y configurará un servidor NFS en el host del grupo centos.
Se puede verificar que el puerto 2049 está habilitado y que el directorio /var/nfs_shared existe con permisos 777.

Prueba de playbook de hardening en Ubuntu 

En el bastión ejecutar:

ansible-playbook -i inventory.ini hardening.yml

Esto actualizará el sistema, configurará el firewall UFW, deshabilitará el login de root por SSH y activará fail2ban.

Se puede verificar ejecutando:

sudo ufw status
sudo systemctl status fail2ban

Nota: este README es minimalista y enfocado solo en las pruebas.
