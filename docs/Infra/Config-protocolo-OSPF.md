

## OSPF-IPV4

Supondo que todos os roteadores estejam com seus respectivos IPs

As configurações ocorreram em 
[![Router(config)#](https://i.im.ge/2023/11/13/AQKOoD.Routerconfig.png)]

Ativa o protocolo

    router ospf 10

Quando ativado entra automaticamente no modo de configuração de routeador

[[![conf-router](https://i.im.ge/2023/12/06/EoHn2y.conf-router.png)](https://im.ge/i/EoHn2y)]
a etapa 1,2 e 3 ocorre nesse modo.

1º - Define a priridade do reteador designado (DR), Quanto menor o número id mais prioridade vai ter.

    router-id _._._._ 

        EX: router-id 1.1.1.1

**OBS:** Em caso de mundança de id e importante limpar os preocessos do ospf usando:

    clear ip ospf process

2º - Atribui a interface a uma área OSPF

    network ip mascara_invertida área valor

        EX network 192.168.1.0  0.0.0.255  area 0
                                    |
                                    - Geralmento usamos 255.255.255.0 mas com esse protocolo e invertido 

3º - Configurando rede passiva

    passive-interface tipo placa

        passive-interface g 0/0


Exibe uma tabela do roteadores vizinhos

    show ip ospf neighbor

Exibe informação sobre todos os roteadores da rede

    show ip ospf database

Ver as rotas

    show ip route



## OSPF-IPV6