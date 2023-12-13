

## RIP ipv4

* Em resumo o protocolo RIP emite mensagens de atualização das suas rotas em intervalos 30 segundos.

Supondo que todos os roteadores estejam com seus respectivos IPs

Entre no modo root [[![Router#](https://i.im.ge/2023/11/13/AQKrmM.Router.png)](https://im.ge/i/AQKrmM)] usando o _'enable'_

E depois no modo de config
[![Router(config)#](https://i.im.ge/2023/11/13/AQKOoD.Routerconfig.png)]
usando '*configure terminal*' 

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

    do show ip protocols

Nessa foto vai mostrar:

* Protocolo
* Versão do protocolo enviado/recebido
* Ips compartilhados
* Último compartilhamento

[![Captura de tela 2023-12-07 220018](https://i.im.ge/2023/12/08/ESxzRc.Captura-de-tela-2023-12-07-220018.png)](https://im.ge/i/ESxzRc)

Usando o comando abaixo vai mostrar os status de redes

    show ip route

Observer que a letra 'R' indica os compartilhamentos que houve na rede

[![rotas](https://i.im.ge/2023/12/06/EoJtKS.rotas.png)](https://im.ge/i/EoJtKS)

**OBS:** Esse (| begin Gateway) e apenas um especificador, para quem usa linux e o mesmo do (grep)

- Essa etapa geralmente se usan quando há algum roteador com caminho para internet ou nuvem.

E importante que uma rota padrão seja propagada na rede para possíveis saídas a internet:

    ip route 0.0.0.0  0.0.0.0  interface_de_rede_de_saido_do_seu_roteador

        EX: ip route 0.0.0.0  0.0.0.0  0/0

Caso queria configurar um rota padrão para uma rota especifica basta apenas adicionar o ip de destino
 
    ip route 0.0.0.0  0.0.0.0  interface_de_rede_do_seu_roteador  ip_da_interface_de_rede_de_destino

        EX:  ip route 0.0.0.0  0.0.0.0  0/0  192.168.1.1

Por motivos de seguraça existe a configuração de interface passiva, essa configuração ocorre nesse modo:
[![conf-router](https://i.im.ge/2023/12/06/EoHn2y.conf-router.png)](https://im.ge/i/EoHn2y)

Configura dessa maneira:

    passive-interface placa_do_roteador

        EX: passive-interface 0/0

O que acontece, apenas as informações de rotas, não serão enviadas por essa rede, ou seja, diminue:

* Uso de largura de banda
* Uso de recursos de rede
* É risco de segurança


## RIP ipv6

A configuração vai ocorrer no modo:[![Router(config)#](https://i.im.ge/2023/11/13/AQKOoD.Routerconfig.png)]

1º - Vamos ativar o roteamento do protocolo ipv6 usando:

    ipv6 unicast-routing

2º - Escolher a interface que vai fazer o compartilhamento

    interface tipo placa

        EX: interface gigabitEthernet 0/0
        Abreviado: interface g 0/0

3º - Ativar o compartilhamento na interface

    ipv6 rip nome_processo enable

**OBS:** Esse **"nome_processo"** e um nome que você vai dar para o processo que sera criado no roteador e todas a interfaces devem ter o mesmo nome de processo.

    EX: ipv6 rip amendoim enable