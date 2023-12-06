Supondo que todos os roteadores estejam com seus respectivos IPs

Entre no modo root usando o _'enable'_

[[![Router#](https://i.im.ge/2023/11/13/AQKrmM.Router.png)](https://im.ge/i/AQKrmM)]

Nesse modo vamos ativar o protocolo _'RIP'_:

    router rip

Após usar o comando acima o roteador entrará neste modo automaticamente

[![conf-router](https://i.im.ge/2023/12/06/EoHn2y.conf-router.png)](https://im.ge/i/EoHn2y)


Por padrão o protocolo vem na versão 1, colocaremos na 2:

    version 2

Agora vamos informar ao roteador quais redes deve anunciar para os outros reteadores

    network ip_da_rede

        EX: network 192.168.1.0

Para verificar as configurações do protocolo usamos:

    show ip protocols

Usando o comando abaixo vai mostrar os status de redes

    show ip route

Observer que os que tem a letra 'R' são os compartilhamentos que houve na rede

[![rotas](https://i.im.ge/2023/12/06/EoJtKS.rotas.png)](https://im.ge/i/EoJtKS)

**OBS:** Esse (| begin Gateway) e apenas um especificador, para quem usa linux e o mesmo do (grep)

E importante que um rota padrão seja propagada na rede para possíveis saídas a internet:

    ip route 0.0.0.0  0.0.0.0  interface_de_rede_de_saido_do_seu_roteador

        EX: ip route 0.0.0.0  0.0.0.0  g0/0

Caso queria configurar um rota padrão para uma rota especific
 

Por motivos de seguraça existe a configuração de interface passiva essa configuração ocorre nesse modo:
[![conf-router](https://i.im.ge/2023/12/06/EoHn2y.conf-router.png)](https://im.ge/i/EoHn2y)

E feita dessa maneira

    passive-interface placa_do_roteador

        EX: passive-interface g0/0

O que acontece, apenas as informações de rotas não serão enviadas para essa rede, ou seja, diminue:


* Uso de largura de banda
* Uso de recursos de rede
* É risco de segurança