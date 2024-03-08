-   Para instalar o code-server vamos utilizar o seguinte comando:

        curl -fsSL https://code-server.dev/install.sh | sh

        Quando finalizar a instação vamos vicular ao seu usuário

        systemctl restart ...

-    Após a instalação vamos configurar.

        Utilizando o usuário criado na etapa do WP-CLI vamos entrar no seguinte arquivo para edição
        usando seu editor preferido ex:nano,micro(no meu caso e o VIM) entre em:

        OBS: user=Seu usuário criado

            seu_editor /user/.config/code-server/config.yaml

        Aparecerar as seguintes variáveis:

        - bind-addr: troca 172.0.0.1 pelo ip da sua máquina ou contêiner.

        - auth: Se caso queira que peça senha coloque depois e (auth:) caso não, coloque (none).

        - password: Deixa como está.

        - cert: Deixa como está.

            bind-addr: Seu_ip:8080
            auth: none
            password: ...
            cert: ...

        - Após salvar restart o serviço usando:

            systemctl restart code-server@user.service

        Agora e só inserir em seu navegador seu (ip:porta) que vai entrar no code-server 

                EX: 192.168.1.1:8080

Já em seu code-server siga as seguintes etapas.

- Vá nas 3 listas no canto superior esquerdo -> File -> Open Folder e abrira essa tela

[![Screenshot_2023-11-09_19-22-53](https://i.im.ge/2023/11/10/ybJzgq.Screenshot-2023-11-09-19-22-53.jpg)](https://im.ge/i/ybJzgq)

            - Clique no diretório que esta o seu site de documentação e depois em OK

            - No canto esquerdo ficara assim:

[![Screenshot_2023-11-09_19-25-42](https://i.im.ge/2023/11/10/ybnxkr.Screenshot-2023-11-09-19-25-42.jpg)](https://im.ge/i/ybnxkr)

            - Clique em docs e haverá um arquivo chamado (index.md) e importante não apaga-lo pois, seu site não será carregado em caso de uso de tema.

            - Para criar outras páginas, basta criar arquivos dentro do diretório (docs) que aparecerar no site.

- Um comando para ver em tempo real as alterações e:

        Vá nas 3 listas no canto superior esquerdo -> terminal -> abrir teminal integrado

        Digite: 
            - mkdocs server

        Após carregar irá dar uma opção para abrir um nova aba 

        Para parar de carregar e só ir até o terminal, clicar nele é da Ctrl + C




            
