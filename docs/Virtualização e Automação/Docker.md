1º - Cria um arquivo Dockerfile e dentro dele será feito as configurações do seu container opções mais usadas

Informa a imagem e a versão da mesma

    FROM Imagem:versão

Informa os comandos que queira usa durante o UP do conteiner

	RUN Comandos 

Copia um arquivo da máquina real para o conteiner

	COPY /caminho/do/arquivo.txt /caminho/destino/no/container/arquivo.txt

Expõe portas se caso necessário

	EXPOSE Nº da porta

Executa comandos quando o conteiner inicia

    CMD ['comando']

## **Comandos do Docker**

Exibe as imagens usadas

    docker image ls

Build uma imagem

    docker build -t nome_do_arquivo . 

Altera o nome

    docker run --hostname new_name old_name

linka dois container pelo nome

    docker run -ti --link container1 --name container2 nome_container

Passa um servidor dns

    docker run -ti -dns dns_server nome_container   

Expõe uma porta para o container 

    docker run -ti --expose port name_container

Binda ou redirecionar o tráfego de portas.

    docker run -ti -p port_host:port_container nome_cotanier

**OBS:** Essas duas etapas necessita o Iptables

* Add um mac ao continer.

        docker run -ti --mac-address mac nome_container

* O ip da máquina real se torna do docker

        docker run -ti --net-host nome_container


2º - Mostras as VMS

    docker container ls [-a]

        -a: Mostrar todas as Vms inativa e ativas

3º - Cria um container 

    docker container run [-ti,-d] container

    -ti: Cria e conectar com um terminal no container

    -d: Roda em modo daemon (2º Plano)

4º - Entra no container

    docker container attach ID

5º - Sai sem matar o container

    Ctrl + P + Q

6º - Executa comandos no container

    docker container exec -ti ID comando

7º - Para o serviço

    docker container stop ID

8º - Inicia o container

    docker container start ID

9º - Pausa o container

    docker container pause ID

10º - Despausa o container 

    docker container unpause ID

11º - Remove o container

    docker container rm ID

12º - Remove uma imagem do conainer 

    docker rmi ID

13º - Mostra informações do container

    docker container inspect ID

14º - Exibe os logs do container

    docker container logs -f ID

15º - Exibe o percentual de uso do container

    docker container stats ID