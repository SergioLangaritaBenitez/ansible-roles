# Prerequisitos
- Vagrant
- Ansible


# Deplegar maquinas

La variable `nodes` en el fichero de Vagrant indica el número de máquinas a desplegar
la dirección para acceder a las máquinas empieza por `192.168.56.2`.
Usar el siguiente comando para el despliegue de maquinas:

```
vagrant up
```

Para aplicar una receta de ansible utilar el siguiente commando:

```
ansible-playbook -i inventory ansible-roles.yaml
```


# Roles creados

- [x]  Docker 
- [x]  Jupyter                                   #http://192.168.56.2
- [x]  María db
  - [x]  Normal                                 #mysql -u user -h 192.168.56.2  -p
  - [x]  Docker                                 #mysql -u user -h 192.168.56.2  -p
- [x]  Posgres
  - [x]  Normal                                  #psql  -h 192.168.56.2 -U admin testdb
  - [x]  Docker                                  #psql  -h 192.168.56.2 -U admin testdb
- [ ]  Mongo 
  - [x]  1 Nodo                                  #mongo (no tiene contraseña, no se ha comprobado si se accede desde remoto)          
  - [ ]  Replica & Sharding
- [ ]  Cassandra
  - [x]  1 Nodo                                  cqlsh (no tiene contraseña,no se ha comprobado por cqlsh en remoto)
  - [ ]  Cassandra cluster
- [x]  Nagios
- [ ]  Kubernetes                                 #Fallo
- [ ]  Spark                                      #https://data-flair.training/blogs/install-apache-spark-multi-node-cluster/
- [ ]  Kafka
  - [ ]  1 Nodo                                  
  - [ ]  Varios Nodos




ansible-galaxy collection install community.docker
ansible-galaxy collection install community.postgresql
ansible-galaxy collection install ansible.posix
ansible-galaxy collection install community.general
