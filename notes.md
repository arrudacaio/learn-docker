# Docker Mastery 

* Docker command line structure
  * ``docker < command > <sub-command > (options) `` 

### Image vs. Containers

- An image **is the application** we want to run.
- A container is **an instance of that image running** as a process
- You can have many containers running off the same image

## Como startar um novo container a partir de uma imagem?
  - Example:  
    - ``` docker container run --publish 80:80 nginx```

Ao rodar este comando acima, ocorreu os seguintes passos:
- 1) Foi baixado a imagem **nginx** do dockerhub
- 2) Iniciou um novo container (um novo processo) a partir dessa imagem
- 3) O comando --publish expôs minha porta local 80 em minha máquina local e enviou todo o tráfego dele para o executável em execução dentro desse container na porta 80.
- 4) Resumindo: A porta 80 é aberta no IP do host E todas as rotas trafegam para o IP do container, na porta 80

Caso não queira que os logs fiquem aparecendo no terminal, voce pode rodar o container em background utilizando a flag: 
- **--detach**

## Para listar todos os containers: 
- ```docker container ls``` ou na versão antiga --> ```docker ps```  
  
## Para parar um container: 
- ```docker container stop <container_id>``` 

## Run vs. Start
- O comando ```docker container run ...``` sempre vai startar um novo container
- O comando ```docker container start <container_id>``` vai iniciar um container que já existe

## Exibir logs de um container
- Através do comando ```docker container logs <container_id || name_container>``` 

## Remover um ou mais containers
- Através do comando ```docker container rm <container_id>``` 
- Só é possível remover um container que está em execução utilizando a flag **-f** que irá forçar a exclusão.


## O que acontece quando rodamos o comando: 
  ```docker container run```

1) Busca-se a imagem localmente, em um "image cache" se não encontrar a imagem, nada acontece.
2) Então busca-se essa imagem em um repositório remoto de imagens, que por padrão é o Docker Hub
3) É baixado a última versão da imagem (latest version), caso não especifiquemos a versão.  
4) Um novo container baseado naquela imagem é criado e prepara-se para startar.
5) O container recebe um *virtual ip* dentro do docker engine
6) Abre-se a porta 80 no host e encaminha para a porta 80 no container.
7) O container é iniciado usando o CMD da imagem (do dockerfile).