# Docker con Ansible y dos nodos
## Docker lab with Ansible and two target machines
- This code create three docker images, one as an Ansible controller and two target machines (Rocky Linux 8 OS).
  
- Clone this repository and execute the following command:
  
`docker compose up -d`

- Connect to Ansible container:
```
docker exec -it ansible_lab /bin/bash
```
- Check target machine's connection and run playbook:
```
ssh server01
exit
ssh server2
exit
ansible-playbook -i hosts playbook. yml
```

## Construir el laboratorio con Ansible y dos containers Docker:
- El objetivo de este repositorio es construir un contenedor Docker con Ansible y dos nodos.Como sistema operativo se utiliza Rocky Linux 8 mediante la imagen oficial de <https://hub.docker.com/_/rockylinux>.
- Se instalan los paquetes necesarios y se configuran las llaves para conectarse por ssh entre los tres contenedores.
- Finalmente se ejecuta un playbook de Ansible como prueba, que creará el fichero hola_mundo.txt en los dos nodos. 

- Estructura de directorios:
```
├── Docker
│   ├── Ansible_Control_node
│   │   └── Dockerfile
│   └── Target_Server
│       └── Dockerfile
├── docker-compose.yml
├── hosts
└── playbook.yml
```

### Instrucciones:
```
docker compose up -d
```
- Conectarse al contenedor Ansible:
```
docker exec -it ansible_lab /bin/bash
```
- Comprobar conexión a los nodos y ejecutar el playbook de Ansible:
```
ssh server01
exit
ssh server2
exit
ansible-playbook -i hosts playbook. yml
```
  
- Adaptado de: <https://www.devopsroles.com/devops-use-docker-to-hands-on-ansible/> 
  
