

##**Instalando**  

Para instalar o squid no linux utilizamos o comando padrão (Baseados no Debian)

    apt install squid

Durante a instalação será criado várias arquivos e diretórios, entre eles:

    - debian.conf (O nome varia dependendo da distro)

    - access.log

Aqui uma ilustração mostrando seus caminhos (Usando o comando *tree*)

[![Tree-squid](https://i.im.ge/2023/11/22/A8DjpJ.Tree-squid.jpg)](https://im.ge/i/A8DjpJ)

## **Configurando**

No arquivo *debian.conf* será feito nossa acl (Access Control List)