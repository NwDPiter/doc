
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

Os passos do Switch até a atapa 6 também funcionam no roteador

0º - Entre no modo root usando o '*enable*'

Ficara assim:
[[![Router#](https://i.im.ge/2023/11/13/AQKrmM.Router.png)](https://im.ge/i/AQKrmM)]

Ao entra no modo de configuração de terminal usando '*configure terminal*' 

Ficara assim:
[![Router(config)#](https://i.im.ge/2023/11/13/AQKOoD.Routerconfig.png)]

### **-  (ipv4)**

1º - Configurando a interface de rede

    interface tipo nº/nº

        EX: interface gigabitethernet 0/1 
        
Ao entrar na interface ficara assim:
[[![config-if](https://i.im.ge/2023/11/13/AQKuWY.config-if.png)](https://im.ge/i/AQKuWY)]

2º - Enderaça a interface  
    
    ip address ip mask

        EX: ip address 192.168.0.1 255.255.255.0

3º - Adiciona rotas ao roteador

    ip route destino mascara prox_salto [metrica]

        EX: ip route 192.168.1.1  255.255.255.0  10.0.0.4  [2]

4º - Adiciona rota padrão no ipv4

        ip route 0.0.0.0. 0.0.0.0 ip_destino

        EX: ip route 0.0.0.0. 0.0.0.0  192.168.1.1

4º - Verifica as config de interface

    show ip interface brief

5º - Verifica as rotas do roteador 

    show ip route

6º - Ligar e desligar

    Ligar = no shutdown
    Desligar = shutdown

7º - Salva as configurações

    do write   

8º - Descrição para interface

    description 'texto'

### **-  (ipv6)**

1º - Habilitar a função de roteamento unicast IPv6

Nesse modo:[![Router(config)#](https://i.im.ge/2023/11/13/AQKOoD.Routerconfig.png)] use o comando:

    ipv6 unicast-routing

2º - Configurar a interface de rede com um endereço IPv6

Nesse modo:[[![config-if](https://i.im.ge/2023/11/13/AQKuWY.config-if.png)](https://im.ge/i/AQKuWY)] use o comando:

    ipv6 address IPV6/Mascara

        EX: ipv6 address 2001:0DB8:AAAA::1/64

3º - Adiciona rotas em IPV6

    ipv6 route IPv6/Mascara  ip_destino metrica

        EX: ipv6 route 2001:0DB8:AAAA::0/64  2001:0DB8:BBBB::1  1     

4º - Adiciona rota padrão em IPV6

    ipv6 route ::/0  ip_destino

        EX: ipv6 route ::/0  2001:0DB8:BBBB::1

5º - Verifica as config de interface

    show ipv6 interface brief

6º - Verifica as rotas IPV6 do roteador 

    show ipv6 route

7º - Salva as configurações

    do write

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