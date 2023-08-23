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

- [ ]  María db
  - [x]  Normal                                 #mysql -u realuser -h 192.168.56.2  -p
  - [ ]  Docker                                 #El docker no se mantiene
- [x]  Posgres
  - [x]  Normal                                  #psql  -h localhost -U admin testdb (falta psql en remoto) 
  - [x]  Docker                                  #psql  -h 192.168.56.2 -U admin testdb
- [ ]  Mongo 
  - [x]  1 Nodo                                  #mongo (no tiene contraseña, no se ha comprobado si se accede desde remoto)          
  - [ ]  Mongo atlas
- [x]  Docker 
- [x]  Jupyter                                   #http://192.168.56.2

- [ ]  Cassandra
  - [x]  1 Nodo                                  cqlsh (no tiene contraseña,no se ha comprobado por cqlsh en remoto)
  - [ ]  Cassandra cluster

- [x]  Nagios
- [ ]  Kubernetes