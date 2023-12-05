## **Instalação**


Nessa primeira etapa e feita as instalações das dependências para o samba.

* Samba
* Krb5-config
* smbclient

Para começar vamos altera o nome da nossa máquina para um domínio, editando o arquivo /etc/hostname

    EX: berlin.alemanha.lab

Após isso, insira seu 'domínio e o primero nome dele' no aquivo /etc/hosts, como e visto na 2º linha.

[![hosts](https://i.im.ge/2023/12/05/CePRt6.hosts.jpg)](https://im.ge/i/CePRt6)

Agora vamos configura o samba usando o seguite comando:

    samba-tool domain provision --use-rfc2307 --interactive


