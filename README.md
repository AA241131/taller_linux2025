# Universidad ORT Uruguay

# Facultad de Ingeniería: Escuela de Tecnología

# Taller Servidores Linux

Andrés Acosta Andrade N.º 241131
Martina De Leon Balbiani N.º 254416


`git@github.com:AA241131/taller_linux2025.git`

11/08/2025

#### Modificaciones necesarias para correr las playbooks

1. Copiar el repositorio 

    `git clone git@github.com:AA241131/taller_linux2025.git`

2. Modificar las ips en el archivo `inventory.ini` para reflejar el laboratorio propio.

    Contenido de `~/taller_linux2025/inventory.ini`:

    ```
    [Centos]
    centos01 ansible_host=192.168.1.2

    [Ubuntu]
    ubuntu01 ansible_host=192.168.1.3

    [webserver]
    centos01

    [Linux:children]
    Centos
    Ubuntu

    [all:vars]
    ansible_user=sysadmin
    ```

3. Ejecutar `ansible-galaxy collection install -r requirements.yml` para      instalar `ansible.posix`, requerido por el módulo de `firewalld`.
