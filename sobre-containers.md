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
  