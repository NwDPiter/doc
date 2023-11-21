###Copiar e alterar o arquivo (000-default.conf) com nome (www.conf e  docs.conf) no diretório /etc/apache2/sites-available.

      -	cd /etc/apache2/sites-available

      -	cp 000-default.conf  www.conf  
      
      -	cp 000-default.conf  docs.conf

###OBS  

    -   Alterar o Documentroot para o seu diretório do seu site 

	-   Ex: Documentroot:  /var/www/diretório_do_site

    -   Altere o NameServer para o url que você deseja para o seu site

    -   EX: NameServer www.exemplo.lab


Ficara assim no www.conf:   
[![Screenshot_2023-11-21_19-44-04](https://i.im.ge/2023/11/22/A87Hmz.Screenshot-2023-11-21-19-44-04.jpg)](https://im.ge/i/A87Hmz)
    
###OBS: No caso da criação de um site usando o (mkdocs) o documentroot apontara dessa forma.

    -   Ex: Documentroot:  /var/www/docs/site

Ficara assim no docs.conf:   
[![Screenshot_2023-11-21_19-43-23](https://i.im.ge/2023/11/22/A87pZ6.Screenshot-2023-11-21-19-43-23.jpg)](https://im.ge/i/A87pZ6)

###Fazer um link de (www.conf e docs.conf) para /etc/apache2/sites-enabled.

    -   cd /etc/apache/sites-enabled

    -   ln -s /etc/apache2/sites-available/www.conf

    -   ln -s /etc/apache2/sites-available/docs.conf

 				    OU

	-   a2ensite nome_do_arquivo