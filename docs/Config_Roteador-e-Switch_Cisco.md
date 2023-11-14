
## **Configurando um Switch**

0º- Entra no modo 'root' e no modo de configuração 

    User simples = Name>
    User Super = Name#

    enable = acessa modo 'root'

    configura terminal = Entra no modo de configurações

1º - Alterar nome do roteador 
   
    hostname nome

        EX: hostname R1 : altera o nome do roteador para R1

2º - Adiciona senha para acessar o console

    line console 0
     |- password 'senha'
     |- - login

3º - Protege o modo privilegiado (#)

    enable secret 'senha'

4º - protege conexões ssh/tealnet

    line vty 0 15           seleciona as 16 vty(Virtual Terminal Lines) usadas para conexões ssh
     |- password 'senha'
     |- - login

5º - Criptografa as senhas

        service password-encryption

6º - Coloca um banner ao logar no Switch

    banner motd '#mensagem#'

7º - Configura a interface do Switch

    interface vlan 1,2,3... quantas tiver escolha uma
     |- ip address ip mask
     |- - no shutdown

**obs: (no) faz o inverso**

8º - Comando que salva as config

    copy running-config startup-config

9º - Atribuir um gateway padrão para o switch

    ip default-gateway ip



## **Configurando um Roteador**

São os mesmos passos do Switch até a atapa 7 ou seja funciona até a 6

0º - Entre no modo root usando o '*enable*'

Ficara assim:
[[![Router#](https://i.im.ge/2023/11/13/AQKrmM.Router.png)](https://im.ge/i/AQKrmM)]

Ao entra no modo de configuração de terminal usando '*configure terminal*' 

Ficara assim:
[![Router(config)#](https://i.im.ge/2023/11/13/AQKOoD.Routerconfig.png)]

São os mesmos passos do Switch até a atapa 7 ou seja funciona até a 6

1º - Configurando a interface de rede

    interface tipo nº/nº

        EX: interface gigabitethernet 0/1 

Ficara assim:
[[![config-if](https://i.im.ge/2023/11/13/AQKuWY.config-if.png)](https://im.ge/i/AQKuWY)]

2º - Descrição para interface

    description 'texto'

3º - Enderaça a interface  
    
    ip address ip mask

4º - Ligar e desligar

    Ligar = no shutdown
    Desligar = shutdown

5º - Verifica as config de interface

    show ip interface brief
   
6º - Adiciona rotas ao roteador

    ip route destino mascara prox_salto [metrica]

    Destino = Rede de destino
    Mascara = Mascara da rede de destino
    prox_salto = ip da interface de chagada do roteador de destino
    metrica = Por quantos roteadores o pacote irá passar

        EX: ip route 192.168.1.1  255.255.255.0  10.0.0.4  [2]

7º - Verifica as rotas do roteador 

    show ip route

## **Configurando o ssh**

1º - Coloca um nome para o ip (DNS)

    ip domain-name 'nome'

2º - Gera um par de chaves RSA

        crypto key generate rsa 

    Vai perdir um valor de criptografia

        1024

    Se caso queria remover essa chave 

        crypto key zeroize rsa

3º - Cria um login e senha

    username 'nome' secret 'senha'

4º - Ativa o protocolo e exige login

    line vty 0 15
     |- transport input ssh 
     |- - login local
     |- - - exit

5º - Ativa a versão 2 do ssh 

    ip ssh version 2
        exit