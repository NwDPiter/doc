
## Configurando um Switch

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



## Configurando um Roteador


São os mesmos passos do Switch até a atapa 7 ou seja funciona até a 6

1º - Configurando a interface de rede

    interface tipo nº/nº

        EX: interface gigabitethernet 0/1 

2º - Descrição para interface

    description 'texto'

3º - Enderaça a interface  
    
    ip address ip mask

4º - Reinicia

    no shutdown

5º - Verifica as config de interface

    show ip interface brief

## Configurando o ssh

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