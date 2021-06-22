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
