`docker run`

`-d` = Deattach

`-P` = Gera uma porta automática

`-p` = Gera uma porta que voce desejar. Ex:8080:80 - Usará a sua porta 8080 para acessar a porta 80 do container

`--name` = Voce pode dar um nome ao container

`-e` = Define uma váriavel de ambiente. Ex: AUTHOR="Luiz Gasparino"

`docker ps`

`-a` = Lista todas as instâncias, rodando ou não.

`-q` = Lista apenas os IDs dos containers

`docker container prune` = Exclui todos os container parados

`docker port` = Serve para ver a porta de algum container rodando

- `docker stop -t 0 $(docker ps -q)`
