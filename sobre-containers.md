## Containers não são mini-vm's
* Os containers são apenas **processos** rodando sobre o seu sistema operacional host.
* Limitados a quais recursos eles podem acessar


## Alguns comandos interessantes em cima dos containers
* Para listar todos os processos que estão rodando dentro de um container 
  - ```docker container top <container>```

* Para inspecionar dados referentes a um container (Usado para saber como um container foi configurado e seus metadados) 
  - ```docker container inspect <container>```

* Ver a performance dos containers e quanto recurso da máquina eles estão consumindo
  - ```docker container inspect <container>```
  

Muitas pessoas utilizam o sistema operacional **Alpine** por ser uma distro linux extremamente leve e que também é focada em segurança.

Utilizando algumas imagens, como o Alpine, você não conseguirá rodar o container de forma iterativa usando o bash. Neste caso, a imagem do Alpine é tão simplório que não possui bash, e nesse caso deve-se utilizar o *sh* para rodar iterativamente o container.

Exemplo que não irá funcionar: <br/> 
```docker container run -it --name alpine alpine bash```