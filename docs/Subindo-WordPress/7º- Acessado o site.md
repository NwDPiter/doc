Insira no browser o domínio que você pôs no arquivo www.conf na sessão de ServerName: 

- Abrirar o site do WordPress e irá pedir:
    
    OBS: Essa informações foram criadas na etapa 4

        - Nome do bando de dados que foi criado

        - Nome do usuário criado para o bando de dados 

        - E a senha inserida para o usuário na criação do banco de dados

        - As outras informações ficam como estão...
        

Próxima Página

    -  Configurando um usuário(ADM) para logar no site do WordPress
            
            -  Linha 1
                Insira o título do site
                    
            -  Linha 2
                Insira o nome do usuário 'ADM'

            -  Linha 3
                Insira a senha de login do usuário para o WordPress

            -  Linha 4
                Insira um E-mail 

            -  Linha 5
                E uma opção para aumentar a seguraça no seu WordPress

            -  Linha 6 
                Instale o WordPress

    -   Agora estando na tela de login 
            
            -   Informe o usuário e a senha que foram criadas na página anterior


Página do Docs:

    Insira no browser o domínio que você pôs no arquivo docs.conf na sessão de ServerName: 

        - Abrirar o site do Docs:

            E está pronto pra visualização...
        

E por fim como analisar os logs de acesso.

    Os logs no linux por padrão ficam em:

         /var/log
Insira no browser o domínio que você pôs no arquivo www.conf na sessão de ServerName: 

- Abrirar o site do WordPress e irá pedir:
    
    OBS: Essa informações foram criadas na etapa 4

        - Nome do bando de dados que foi criado

        - Nome do usuário criado para o bando de dados 

        - E a senha inserida para o usuário na criação do banco de dados

        - As outras informações ficam como estão...
        

Próxima Página

    -  Configurando um usuário(ADM) para logar no site do WordPress
            
            -  Linha 1
                Insira o título do site
                    
            -  Linha 2
                Insira o nome do usuário 'ADM'

            -  Linha 3
                Insira a senha de login do usuário para o WordPress

            -  Linha 4
                Insira um E-mail 

            -  Linha 5
                E uma opção para aumentar a seguraça no seu WordPress

            -  Linha 6 
                Instale o WordPress

    -   Agora estando na tela de login 
            
            -   Informe o usuário e a senha que foram criadas na página anterior


Página do Docs:

    Insira no browser o domínio que você pôs no arquivo docs.conf na sessão de ServerName: 

        - Abrirar o site do Docs:

            E está pronto pra visualização...
        

E por fim como analisar os logs de acesso.

    Os logs no linux por padrão ficam em:

         /var/log

    Nesse caso como estamos usando o apache2 iremos ver os logs de acesso dele.

        /var/log/apache2/access.log

    Para verificar em tempo real utilizaremos o seguinte comando:

        tail -f /var/log/apache2/access.log | ccze
    
    OBS: O ccze e apenas para colorir os log se for usar verifique se está instalado.
    Nesse caso como estamos usando o apache2 iremos ver os logs de acesso dele.

        /var/log/apache2/access.log

    Para verificar em tempo real utilizaremos o seguinte comando:

        tail -f /var/log/apache2/access.log | ccze
    
    OBS: O ccze e apenas para colorir os log se for usar verifique se está instalado.