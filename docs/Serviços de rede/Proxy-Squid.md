

##**Instalando**  

Para instalar o squid no linux utilizamos o comando padrão (Baseados no Debian)

    apt install squid

Durante a instalação será criado várias arquivos e diretórios, entre eles:

    - debian.conf (O nome varia dependendo da distro)

    - access.log

Aqui uma ilustração mostrando seus caminhos (Usando o comando *tree*)

[![Tree-squid](https://i.im.ge/2023/11/22/A8DjpJ.Tree-squid.jpg)](https://im.ge/i/A8DjpJ)

**OBS:** Por padrão o squid nega todo o acesso quando é instalado, para desabilitar vá em:

    -   /etc/squid/squid.conf

Proucure a linha que tem _http_access **deny** all_ e troque para **allow** isso vai permitir o acesso para todos os site, desse jeito:

[![Screenshot_2023-11-22_19-12-37](https://i.im.ge/2023/11/23/AK3UI4.Screenshot-2023-11-22-19-12-37.jpg)](https://im.ge/i/AK3UI4)

Ou deixar como está e permita apenas os sites específicos no processo de configuração.

## **Configurando**

No *'debian.conf'* será adicionado nossa acl (Access Control List) o padrão de construção é:

    -     acl NOME_DA_ACL TIPO_DA_ACL parâmetro

        EX: acl exemplo dst www.facebook.com

Existe vários (TIPO_DA_ACL)

    -   dst = O parâmetro sera um host,rede ou domínio ex: www.youtube.com

    -   url_regex = O parâmetro sera um nome ou palavras 

    -   port = O parâmetro sera uma porta ex: 80

    -   Para ver mais entre em (ACLS Squid)

O arquivo por padrão vem assim:

[![Captura de tela 2023-11-21 213021](https://i.im.ge/2023/11/22/A8LYmY.Captura-de-tela-2023-11-21-213021.png)](https://im.ge/i/A8LYmY)

Aqui um exemplo de um acl criada:

[![Captura de tela 2023-11-21 213400](https://i.im.ge/2023/11/22/A8LfHf.Captura-de-tela-2023-11-21-213400.png)](https://im.ge/i/A8LfHf)


Neste exemplo o nome da acl é *'sites_block'*. É para bloquear ou permitir o site o padrão de construção é:

    -   http_access permissão NOME_DA_ACL

Tipos de permissão 

    deny: Nega o acesso                 

    allow: Permite o acesso

* **NOME_DA_ACL:** Nesse caso foi usado sites_block

O exemplo ficará assim:

[![Captura de tela 2023-11-21 213424](https://i.im.ge/2023/11/22/A8LVA1.Captura-de-tela-2023-11-21-213424.png)](https://im.ge/i/A8LVA1)

Agora e só ir no navegador e configura o proxy, por padrão: 

1.Abra o navegador.

2.No menu, selecione Configurações ou Opções.

3.Na seção Rede, selecione Configurações de proxy.

4.Marque a caixa Usar um servidor proxy.

5.Insira o endereço IP do servidor proxy e a porta.

(Pode variar entres os navegadores)

## **Logs**

Para verificar os logo e simples, lá em cima vimos o arquivo 'access.log' e onde ele fica, para verificar em tempo real use:

    tail -f /var/log/squid/access.log 

OBS: caso queira deixar os logs coloridos use:

    tail -f /var/log/squid/access.log | ccze 

so for usa o 'ccze' primeiro verifique se está instalado.

