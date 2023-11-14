**OBS**: Essa documentação e para fins didáticos

Utilitarios do NMAP


Envia um ping para todos da rede e retorna se esta ativo ou não 

    nmap -sP [endereço IP da rede]

        EX: nmap -sP 192.168.1.0/24

    Irá enumerar todos os hosts ativos na rede.

Retorna informações sobre os hosts ativos

    nmap -sS [endereço IP da rede]

        EX: nmap -sS 192.168.1.0/24

    Enviará pacotes SYN aos hosts ativos e esperar por respostas. Se um host responder, o Nmap irá determinar o seu tipo de sistema operacional e versão.

Para obter informações mais detalhadas sobre os hosts ativos

    nmap -sT [endereço IP da rede]

        EX: nmap -sT 192.168.1.100

    Enviará pacotes TCP de três vias aos hosts ativos. Se um host responder, o Nmap irá determinar o seu tipo de sistema operacional, versão e portas abertas.

Para escanear portas específicas em um host.

    nmap -p [portas] [endereço IP do host]

        Ex: nmap -p 80,443 192.168.1.100

    Este comando irá verificar se as portas 80 e 443 estão abertas no host 192.168.1.100

Para obter mais informações sobre as portas abertas em um host.

    nmap -sV [endereço IP do host]

        EX: nmap -sV 192.168.1.100

    Este comando irá verificar se as portas abertas no host estão mapeadas para serviços específicos.

Para escanear uma rede para vulnerabilidades.

    nmap -sV -sC [endereço IP da rede]

        EX: nmap -sV -sC 192.168.1.100

    Este comando irá verificar se as portas abertas na rede estão mapeadas para serviços vulneráveis.

Para obter mais informações sobre as vulnerabilidades encontradas.

    nmap -sV -sC -oX [arquivo de saída] [endereço IP da rede]

        EX: nmap -sV -sC -oX arquivo.txt 192.168.1.100

    Este comando irá gerar um relatório XML com informações sobre as vulnerabilidades encontradas.