### Passo a Passo

-   Vamos entra no diretório (/var/www) e dar acesso ao usuário criado

        chown user:user  .

-   Logue com o usuário 

        su  usuário_criando

-   E instale o WordPress usando esse comando 

        wp  core  download  - - locale=pt_BR  - - path=nome_site

-   Entre no diretório que você criou usando o comando acima

        cd /var/www/nome_site

-   E de Autorização para fazer a configuração do banco de dados no site

        chmod   777   .
