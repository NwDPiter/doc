-   Fazendo a instalação do WP-CLI e dando permissão.

    ###Entre no diretório

         cd  /usr/local/bin
    ###Instale o WP-CLI usando o curl 
-   Para instalar o code-server vamos utilizar o seguinte comando:

        curl -fsSL https://code-server.dev/install.sh | sh

-    Após a instalação vamos configurar.

        Utilizando o usuário criado na etapa do WP-CLI vamos entrar no seguinte arquivo para edição
        usando seu editor preferido (no meu caso e o VIM) entre em:

        OBS: user=Seu usuário criado
…
            

         curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
    ###Altere o nome do comando 

         mv wp-cli.phar wp

    ###De permissão ao WP-CLI 

         chmod  +x  wp

###Criando usuário para manipular o WP

          useradd -m -s /bin/bash nome_user	

                     OU

          wp user create USER e-mail senha administrator USER -- Nome do user
                           |      |    |          |
                    Nome do user  |Senha do user  |
                                  |               |
                                  |       Função / Papel do user
                           E-mail do user