## Docker Networks
* Cada contêiner é conectado a uma rede virtual privada "bridge"
* Cada rede virtual roteia através do firewall NAT no IP do host
* Todos os containers conectados a rede privada dentro do host podem se comunicar com outro container sem necessitar utilizar o **--publish**. 
  * Uma boa prática para isso é criar uma rede virtual para cada aplicação. 
  * Ex: network "my_web_app" para os containers do mysql, nodejs.

</br>

### Comandos para gerenciamento da network

* Criar uma network  (ou melhor dizendo, as redes): <br/> 
```docker network create --driver```

* Listar as networks (ou melhor dizendo, as redes): <br/> 
```docker network ls```
  
* Inspecionar uma network: <br/> 
```docker network inspect <ID_NETWORK>```
<br/> Este comando irá te retornar dados sobre a network

* Conecta a network com um container específico: <br/> 
```docker network connect <ID_CONTAINER>```
<br/> 
Uma vez conectado, o container poderá se comunicar com outros containeres que estão conectados à rede(network)

<br/> 


### Exemplo de uso: <br/> 
    Uma vez listado todas as redes que estão rodando no meu docker, gostaria de inspecionar uma dessas redes afim de verificar 
    quais containers estão rodando nela: 


    1) docker network ls
    2) docker network inspect bridge


    Após o último comando, será listado no seu terminal um json que contém a informação de quais containers estão ativos nessa rede.


### Exemplo de uso 2: <br/> 
    Gostaria de criar uma network para minha aplicação web e depois criar um container que vá usar essa network.


    1) docker network create <nome_da_rede>
    2) docker run -d --name my_backend --network <nome_da_rede> nginx


    Dessa forma criei uma rede e logo após criei um container que irá fazer uso dessa rede. Portanto posteriormente posso criar um container apenas para o meu front-end e usar a mesma rede que o backend está usando. 