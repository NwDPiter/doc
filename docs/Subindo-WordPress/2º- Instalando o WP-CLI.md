-   Fazendo a instalação do WP-CLI e dando permissão.

    ### Entre no diretório

         cd  /usr/local/bin

    ### Instalação

-   Para instalar o WP-CLI vamos utilizar o seguinte comando:
       
          curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar

    ### Altere o nome do comando 

         mv wp-cli.phar wp

    ### De permissão ao WP-CLI 

         chmod  +x  wp

### Criando usuário para manipular o WP

          useradd -m -s /bin/bash nome_user	

                     OU

          wp user create USER e-mail senha administrator USER -- Nome do user
                           |      |    |          |
                    Nome do user  |Senha do user  |
                                  |               |
                                  |       Função / Papel do user
                           E-mail do user