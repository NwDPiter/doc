###Copiar e alterar o arquivo (000-default.conf) com nome (www.conf e  docs.conf) no diretório /etc/apache2/sites-available.

      -	cd /etc/apache2/sites-available
      -	cp 000-default.conf  www.conf  
      -	cp 000-default.conf  docs.conf

###OBS  

    -   Alterar o Documentroot para o seu diretório do seu site 
	-   Ex: Documentroot:  /var/www/diretório_do_site

###OBS: No caso da criação de um site usando o (mkdocs) o documentroot apontara dessa forma.

    -   Ex: Documentroot:  /var/www/docs/site

###Fazer um link de (www.conf e docs.conf) para /etc/apache2/sites-enabled.

    -   cd /etc/apache/sites-enabled
    -   ln -s /etc/apache2/sites-available/www.conf
    -   ln -s /etc/apache2/sites-available/docs.conf

 				    OU

	-   a2ensite nome_do_arquivo