# learn-docker

### Docker file
* Onde definimos a nossa imagem. 
* Para construir a imagem:
  
  ```docker build -t mysql-image -f caminho_do_dockerfile .``` 
  
    -t (TAG): Determina um nome para a imagem 

    -f (flag): Determina o caminho da pasta raiz até o Dockerfile

    . (ponto): Determina que o contexto para gerar a imagem vai ser da pasta que estou rodando o comando atualmente   

### Para ver as imagens prontas para uso 
```docker image ls``` 

---


### Agora vamos criar nosso container a partir da imagem que acabamos de criar
```docker run -d --rm --rm --name nome_container nome_imagem``` 

* -d : detached, significa que vamos utilizar o container em background

* --name : Definimos o nome do nosso container
  
* --rm : Se tiver um container igual em execução, irá ser removido para que um novo possa ser criado

* nome_container: Nome do container

* nome_imagem: Nome da Imagem



### Executando comandos dentro de um container 
```docker exec -i nome_container comando_a_ser_executado```
* -i : Significa que estamos rodando o comando no modo interativo

### Acessar o shell do container
```docker exec -it nome_container /bin/shell```

Tudo que é feito no container é perdido quando ele é interrompido. Para evitar isso, usamos volumes. 