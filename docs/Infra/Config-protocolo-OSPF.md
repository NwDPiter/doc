

## OSPF-IPV4

Supondo que todos os roteadores estejam com seus respectivos IPs

As configurações ocorreram em 
[![Router(config)#](https://i.im.ge/2023/11/13/AQKOoD.Routerconfig.png)]

Ativa o protocolo

    router ospf 10

Quando ativado entra automaticamente no modo de configuração de routeador

[[![conf-router](https://i.im.ge/2023/12/06/EoHn2y.conf-router.png)](https://im.ge/i/EoHn2y)]
a etapa 1,2 e 3 ocorre nesse modo.

1º - Define a prioridade do roteador designado (DR), Quanto menor o número do id mais prioridade vai ter.

**DR** = E um roteador central que vai receber informações de outros roteadores e realizar calculos de melhores caminhos,melhores liks de rede ,etc..por fim devolver os resultados a cada roteador.

    router-id _._._._ 

        EX: router-id 1.1.1.1  EX: router-id 2.2.2.2 EX: router-id 3.3.3.3  

**OBS:** Em caso de mundança de id e importante limpar os preocessos do ospf usando:

    clear ip ospf process

2º - Atribui a interface a uma área OSPF, FAÇA ISSO EM TODAS AS INTERFACES QUE FOR USAR...

    network ip_da_rede mascara_invertida área valor

        EX network 192.168.1.0  0.0.0.255  area 0
                                    |
                                    - Geralmento usamos 255.255.255.0 mas com esse protocolo e invertido 

3º - Configurando rede passiva;

    passive-interface tipo placa

        passive-interface g 0/0

O que acontece, apenas as informações de rotas, não serão enviadas por essa rede, ou seja, diminue:

* Uso de largura de banda
* Uso de recursos de rede
* É risco de segurança

Exibe uma tabela do roteadores vizinhos

    show ip ospf neighbor

Exibe informação sobre todos os roteadores da rede

    show ip ospf database

Ver as rotas

    show ip route



## OSPF-IPV6