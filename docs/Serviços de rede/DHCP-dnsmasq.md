## Configurando um sevidor DHCP

Em um ambiente linux vamos instalar:

- dnsmasq

1º - Aquivo de configuração do dnsmasq é:

    /etc/dnsmasq.conf

mas, vamos criar um arquivo (exemplo.conf) no diretório (dnsmasq.d)

    /etc/dnsmasq.d/exemplo.conf

todas as configurações no arquivo(exemplo.conf) vai migra para dnsmasq.conf.

2º - Editando o arquivo **exemple.conf** a configuração padrão é essa:

* interface= nome da interface que vai ser dhcp

        EX: interface= eht1

* dhcp-range=ip inicial , ip final , mascara de rede , tempo que o dispositivo fica com o ip

        EX: dhcp-range= 192.168.1.1, 192.168.1.254 , 255.255.255.0 , 12h

* dhcp-option= option , ip do roteador

        EX: dhcp-option= 3 , 192.168.1.254  

            3: Identifica o servidor DNS

* dhcp-option= option , ip do dns  (**Opicional**)

        EX: dhcp-option= 6 , 8.8.8.8

            6: Identifica o servidor DNS

* dhcp-option= option, domínio (**Opicional**)

        EX: dhcp-option= 15, alemanha.lab  

            15: Especifica um domínio se caso você esteja em um

* log-facility= caminho/para/o/log

        EX: log-facility= /var/log/dnsmasq.log

Ficaria assim:

[![Screenshot_2023-12-20_22-05-23](https://i.im.ge/2023/12/21/xXDWlT.Screenshot-2023-12-20-22-05-23.jpg)](https://im.ge/i/xXDWlT)


Agora e só você está na mesma rede que do servidor DHCP e pedir para receber ip em modo DCHP

EX no Windows:

[![tcp](https://i.im.ge/2023/12/21/xXI7vf.tcp.jpg)](https://im.ge/i/xXI7vf)
[![Screenshot_2023-12-20_22-11-28](https://i.im.ge/2023/12/21/xXIISm.Screenshot-2023-12-20-22-11-28.jpg)](https://im.ge/i/xXIISm)
