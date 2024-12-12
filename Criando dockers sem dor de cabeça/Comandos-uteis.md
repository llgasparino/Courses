# Utilizando docker run

> `docker run`

- `-d` = Deattach

- `-P` = Gera uma porta automática

- `-p` = Gera uma porta que voce desejar. Ex:8080:80 - Usará a sua porta 8080 para acessar a porta 80 do container

- `--name` = Voce pode dar um nome ao container

- `-e` = Define uma váriavel de ambiente. Ex: AUTHOR="Luiz Gasparino"

- `-it` = Habilita entrar dentro do terminal da imagem docker

- `-w` = Especifica o Working Directory

# Listar containers

> `docker ps`

- `-a` = Lista todas as instâncias, rodando ou não.

- `-q` = Lista apenas os IDs dos containers

# Deletar containers

`docker container prune` = Exclui todos os container parados

# Informações de porta do container

`docker port` = Serve para ver a porta de algum container rodando

- `docker stop -t 0 $(docker ps -q)`

# Persistência de dados

## Criando um volume

`docker run -it -v "/home/pasta:/var/teste" ubuntu`

- `-v` = Volume. "Caminho dentro da nossa máquina: Caminho no container"

> Outra coisa que podemos fazer é rodar aplicações node dentro do container

`docker run -d -v "E:/llgasparino/Desktop/projeto:/home/projeto" -w "/home/projeto" node npm start`

OU

`docker run -d -v "$(pwd):/home/projeto" -w "/home/projeto" node npm start`

- `-w` = Especifica o Working Directory

# Criando dockerfile

```Dockerfile
FROM node:latest                # Da imagem base node
LABEL author=llgasparino        # Tag author=llgasparino
ENV NODE_ENV=production         # Váriavel NODE_ENV=produção
ENV PORT=3000                   # Váriavel PORT=3000
COPY . /home/projeto            # Copia todos os arquivos da pasta para o local desejado
WORKDIR /home/projeto           # Define o Working directory do projeto
RUN npm install                 # Roda `npm start`
ENTRYPOINT ["npm","start"]      # Primeiro comando a rodar depois do install
EXPOSE $PORT                    # Expõe a porta da váriavel $PORT
```

> docker build -f Dockerfile -t llgasparino/node .

- `-f` = File name, nesse caso não iria precisar pelo nome ser padrão.

# Trabalhando com networks em docker

Cada container criado recebe um ip padrão e eles se conversam

- 172.17.0.1 - 172.17.0.2 - 172.17.0.3...
  > Para verificar `hostname -i` (No ubuntu)

## Criando nossa própria rede

`docker network create --driver bridge minha-rede`

`docker network ls`

`docker run -it --name meu-container-ubuntu --network minha-rede ubuntu`

Podemos nos comunicar sem usar IP e sim hostname
