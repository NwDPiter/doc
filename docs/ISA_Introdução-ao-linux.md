# Introdução ao Linux

##   Manipulação de arquivos ou diretórios#

pipe | : Permite pegar a saída do um comando e direcionar para o próximo

**ls [-l,-t,-S,-r]:** list directory

    -l :list the directory with details

    -t: Classificar por data e hora

    -S: Ordenar por tamanho de arquivo

    -r: Inverte qualquer tipo de classificação

**cd :** Usado para acessar outros diretórios

**touch :** cria um arquivo

**mkdir[-p,-m] :** Cria um diretório

    -p: Cria um diretório entre duas pastas existentes

    -m: Define as permissões do diretório

**pwd :** mostra o caminho do diretório atual

**rm :** remove file’s (-R 'Recursivo' -F 'Executa sem interrupções')

**cd .. :** Volta um diretório

**mv:** move ou renomeia arquivos e diretórios

**diff  [arquivo] [arquivo]:** Faz a comparação entre arquivos

**rmdir :** remove directory

**man comando :** help do comando

**cp nome\_do\_arquivo + destino/ :** cópia de um lugar para outro

**mv :** Move ou renomeia arquivos de diretórios

**wc [-c,-w,-l] Arquivo :** conta a quantidade de caracteres,palavras e linhas

    -C: caracteres

    -W: palavras

    -l: linhas

**find local de busca -name  nome\_do\_arquivo:** procurar arquivos no disco rígido por nome

**head:** pega as 10 primeiras linhas (pro padrão,mas pode ser mais) do arquivo

    head -número_linhas local/do/arquivo

**tail** pega as 10 ultimas linhas de um arquivo

    tail -número_linhas local/do/arquivo

Utilizados para saídas de comandos

    sort : deixar em ordem alfabética, -r (inverte a ordem alfabética)

    nl (number line) : enumera as linha de um arquivo

    cut  -d[O que vai separar] -f [posição/coluna]:  Filtra os nomes exato procurado

    ln [opção (-b ou -s simbólico)]  caminho nome do link : cria atalhos para files ou directory

**echo ‘msg’:** envia uma mensagem para o terminal

**which comando:** procura por comando em diretórios

**./ nome_arquivo:** executa um arquivo
    
    Verifique se o arquivo tem permissão para executar,se não, altere vendo a sessão de Alteração de permissões

**lt:** less than (menor que)

**gt:** greater than (maior que)

**eq:** equal (igual)

**le:** less than or equal (menor ou igual)

**ge:** greater than or equal (maior ou igual)

**nwq:** not equal (não igual)

**read:** ler uma variável

**dd if=origem of=destino bs=:**

    if=diretório: Representa o disco a ser copiado

    of=diretório: Representa o disco que vai receber a cópia

    bs=tamanho disponibilizado para o bloco[M,B,G,T,]

    M: Mega  /  B: Bytes  /  G: Giga  /  T: Tera

**grep [-E,-R,-r,-i,-l,] padrão  arquivo:** procura linhas com padrões específicos em arquivos de textos

    -E: Quando for utilizar expressões regulares estendidas

    -i: Ignora as diferença entre maiúscula e minúscula	

    -l: Exibe o nome do arquivo ao invés da saindo normal do grep

    -r e R: Recursivo

**-------------------------------------------------------------------------------------------------------------**

##   $Expressões Regulares$

***RegEx***

***Busca , válida e substitui***

***Comando relacionado (egrep | grep)***

**^:** Padrão de começo de linha

    Ex: grep ^r /etc/passwd ; Vai mostrar padrões que começam com r.

**$:** Padrão de final de linha

    Ex: grep r$ /etc/passwd ; Vai mostrar padrões que terminam com r.

**Asterisco(*) :** Corresponde a nenhum ou vários caracteres antes do \*

    Ex: grep ro\*t /etc/passwd ; Vai mostrar essa busca com n termos ‘o’ ou nenhum termo ‘o’.

**+ :** Diz que tem uma ou mais caracteres do anterior

    Ex: grep ro+t /etc/passwd ; Vai mostrar apenas se tiver um ou mais caracteres com esse, nunca se não haver nenhum.

**?:** Torna o caractere opcional

    Ex: grep ro?t /etc/passwd ; Vai mostrar o que foi encontrado com e sem a letra ‘o’.

**Ponto(.):** Pode substituir qualquer caractere de acordo com a quantidade de pontos.

    Ex: grep ro.t /etc/passwd ; Vai  mostrar o que foi encontrado com a palavra root.

**[ ]:** Procura por caracteres específicos

    Ex: grep [02] /etc/passwd ; Vai mostrar apenas onde foi encontrado o caractere 0 e 2.

    Ex: grep [0-9] ou [a-z] /etc/passwd ; Vai mostrar todos os caracteres entres os que foi escolhido.

**[^ ]:** Mostra caracteres o que não está nessa lista

    Ex: grep [^Aa] /etc/passwd ; Vai mostrar tudo que não tenha A e a.

**{}:** Multiplica a função anterior

    Ex: grep -e [0]{2} /etc/passwd ; Vai mostrar apenas quando tiver duas ocorrências do caractere 0.

    Ex: grep -e [0-9]{6} ou [a-z]{6}; Em ambas vão mostrar se caso for >= 6 a quantidade de caracteres.

    Ex: grep -e ^[0-9]{6}$ /etc/passwd ; Vai mostrar apenas linhas que possuem 6 caracteres.

**-------------------------------------------------------------------------------------------------------------**

##   Informações da máquina#

**init [0,6]:**  off or reboot

    0: Off machine  

    6:  Reboot

**shutdown [-h,-r] time msg :**  Off or Reboot

    -h: Off machine   -r: Reboot  hh:mm: Hora e minuto que será desligado
    e para aumentar o tempo: shutdown +minutos.

**.  ->** Diretório corrente o que vc está agora

**.. ->** Diretório anterior 

**sources.list:**  onde fica listado os aplicativos da máquina

**uname -a (lsb\_release -a):**  mostra todas as informações sobre o S.O

**time:** mede o tempo de execução de comando

**cal:**  exibe o calendário

**date:**  Vai exibir dia da semana , mês , dia , hora:minuto:segundo , ano e  UTC

**localhost = 127.0.0.1**

**sudo :** permite usuários comum executar comandos como administrador

**shadow :** local onde ficam as senhas

**gshadow :** local onde ficam as senhas dos grupos

**su :**  Diz ao sistema qual usuário você quer ser

**Setuid:**  executa um arquivo como se fosse o dono

**Sergid:**  Executa como se fosse um membro do grupo

**Sticky:**  arquivos com esse bit só pode ser apagado pelo próprio dono

**Tipos de arquivos :** d = diretório, l = link simbólico, c = Dispositivo de

caractere, b = Dispositivo de bloco, s = soquetes, (=) = Pipes

**Shells:** SH,BASH,ASH,ZSH

**-------------------------------------------------------------------------------------------------------------**

## Manipulação de Programas

- Comandos de instalação de programas

**sudo apt-get update:**(Ferramenta de pacote) atualiza a lista de pacotes disponíveis para download

**sudo apt-get upgrade:** Atualiza os pacotes e dependências

**apt-cache search nome:** Find package with this name or your description

**sudo apt install pacote:** Instala o pacote desejado e atualiza se já estive no sistema

**dpkg -l:** Lista os pacotes instalados no linux

- Comandos de remoção de programas

**apt-get remove pacote:** Remove o pacote

**apt-get purge pacote:**  Remova completamente o pacote do sistema

- Comandos para baixar da web

Curl [-o -L -u]: 

    o


Wget [-O -r -l -c --limite-rate=vel]:

    -O: Altera o nome do arquivo baixado

    -r: Liga o download recursivo

    -l: Define o nível de recursividade

    -c: Caso interrompido retorna de onde parou

    --limite-rate: Define a velocidade de download

**-------------------------------------------------------------------------------------------------------------**

##   DIRETÓRIOS PRINCIPAIS#

/diretório raiz;

/boot: Kernel do Sistema;

/proc: Sistema de arquivos virtual de informação do kernel (Armazenar informação sobre os processos)(Criar subdiretórios para cada processo)

/dev: Arquivos de dispositivo de hardware

/tmp: Arquivos temporários

/etc: Arquivos de configuração do sistema

/bin: Comandos essenciais do sistema

/mnt: Ponto de montagem temporário para sistemas de arq.

/opt: Pacotes de software adicional

/sbin: Comandos essenciais de adm. do sistema;

/var: Dados variáveis;

/var/log/syslog: onde fica histórico de eventos ou LOG

/home: Diretório do usuário

E um sistema de :multitarefa, multiusuário, conexão com outros tipos de sistemas operacionais, segurança quanto a proteção de processos executados na memória RAM e open source(Fonte aberta)

**-------------------------------------------------------------------------------------------------------------**



## Criação de grupo


**groupadd** nomedogrupo: cria grupos

**groupdel** : deleta grupos

**groupmod nomedogrupo -n novonome :**altera o nome do grupo

**gpasswd -a  usuário  nomedogrupo:** adiciona o usuário ao grupo

**usermod -aG nome\_do\_grupo nome\_do\_usuario:** adiciona o usuário no grupo

**gpasswd -d usuário nomedogrupo:** retira o usuário do grupo

**gpasswd nomedogrupo :** coloca uma senha no grupo

**roups :** mostra o grupos que o usuário está

**newgrp:** carrega as alterações de grupo


**-------------------------------------------------------------------------------------------------------------**


## Criação de usuário


**useradd** [-m,-s,-c,-g,-G]: cria um usuário

    -m(Cria o diretório home)

    -s(Informar o shell do usuário)

    -c(Informar um comentário sobre o usuário)

    -g(Informar o grupo primário)

    -G(Informar o grupo secundário)

**useradd -m -s /bin/bash -g nomedogrupo(primário) -G nomedogrupo(sercundário) nomedousuário**

**userdel:** remove um usuário

**userdel -r usuários:** apaga o usuário e seu diretório

**usermod nome -l novonome:** altera o nome do usuário

**usermod -g grupo nome:** altera o grupo primário do usuário

**usermod -G (pode ser mais de um grupo) grupo,grupo,grupo usuário:** altera os grupos secundários do usuário

**usermod -d:** Altera o diretório do usuário

**-------------------------------------------------------------------------------------------------------------**

**id:** mostra informações do usuários autenticado

**Who:** mostra informações de usuários conectados atualmente

**passwd :** configura e altera senhas do usuário (INFORMAÇÕES DO USUÁRIOS)

    passwd [-S] usuário: atribui uma senha para o usuário ou caso já tenha pode alterar

**SINTAXE:** Usuário , Status de senha , data , N de dias necessário antes de trocar novamente a senha , N de dias antes da senha expirar , N de dias que o usuário é avisado antes da senha expirar , N de dias que a conta pode fica ativa com a senha expirada

    S: Exibe informações de status sobre sua senha

    P: Indica que há senha

    L: Indica que a senha está bloqueada

    NP: Indica que não há senha


**-------------------------------------------------------------------------------------------------------------**


## Alteração de permissão


**chmod [permissões] arquivo:** Altera as permissões de um arquivo

    -c(Informar os arquivos modificados)

    -v(Descreve as alterações de atributos)

**chmod +rwx:** Adiciona permissão

    r = read = ler
    w = write = escrever
    x = executar

**chmod -rwx:** Retirar permissões

    se você quer tirar a permissão de executar um arquivo use:

    EX: chmod -x nome-do-arquivo

**chown novodono.grupo arquivo:**  altera o dono do arquivo

**chgrp novogrupo arquivo :** altera o grupo do arquivo

**644 **: permissão padrão do arquivo

**755 **: permissão padrão do diretório

**-------------------------------------------------------------------------------------------------------------**

## Gerenciamento de processos

Arquivos relevantes

cmdline: Guarda a linha de comando usada para iniciar o processo

environ: mostra as variáveis de ambiente utilizadas pelo processo

exe: é um link (apontador) para o executável daquele processo

fd: diretório contendo todos os descritores de arquivo

limits: as restrições impostas ao processo(/etc/security/limits.conf)

maps: mapa de memória para os executáveis e bibliotecas

root: apontador para o diretório raíz do processo

mounts: informação sobre os sistemas de arquivo

mem: memória utilizada pelo processo

sched: informações sobre o escalonador e o escalonamento

stat: status do processo

statm: status da memória do processo

**-------------------------------------------------------------------------------------------------------------**

## Informações dos processos

**ps [-a,-u,-x,-l,-e, -f]:** lista os programas em execução

    a: Mostra informações de outros usuários

    u: Mostra o nome de usuário e a hora de início

    x: Mostra os processos não associados ao terminal 	

    l: Mostra com detalhes

    e: Mostra todos os processos ativos

    f: Mostra com mais detalhes

**top [-u, ,-U,-d,-t,]:** mostra todos os processos em execução,sua prioridade varia entre -20(maior prioridade) e 19(menor prioridade)

    -u: Mostra just(apenas) processos de usuários específicos

    -U:Não mostra processos de usuário específicos

    -d:Não atualiza o monitor a cada segundo

    -t: Exibe processo just de terminal especificado

**nice -n ajuste comando:** altera a ordem de processo (Usuários normais apenas entre 0 a 19) (root 19 a -20)

**renice +|- new\_num\_nice [-u, -p, -g] alvos:** altera as prioridades de forma mais específica

    -u: altera as prioridades de processos de um usuário(caso não
    coloque o usuários vai por padrão todos )

    -p: por padrão não precisa colocar apenas informar o PID

    -g: alterar as prioridades de processos de um grupo

**kill:** [opcional] finaliza um processo

    -1:Diz ao processo para desligar ou reiniciar

    -2:igual a utilizar o ctrl + c

    -3:Interrompe um processo e cria uma back(Arquivo dump)

    -9:Finaliza processos obrigatoriamente, com exceção de zumbis

od (-t(Especifica o tipo de saída))  visualizarmos o conteúdo de um arquivo nos formatos hexadecimal, octal, ASCII e nome dos caracteres.

    a(Caracteres)

    c(ASCII),

    o(Octal),

    x(Hexadecimal)

**Ctrl + c:** Finaliza um processo

**Ctrl + z:** Suspende um processo

**nome\_do\_programa &:** executa o programa em BackGround

**bg %[PID]:** Põe o processo em BackGround

**fg %[PID]**: Põe o processo em ForeGround

**jobs [-l]:** mostra os app em bg(BackGround)

    -l: exibe o PID e nome de cada processo

**pidof nome\_do\_processo:** Retorna o pid do processo informando o nome

**uptime [-V]:** Exibe o tempo de funcionamento do sistema e sua carga

    -V: Mostra a versão do comando

**free [-m]:** Exibe a quantidade de memória utilizada no sistema

    m: Mostra em megabytes

**vmstat:** Exibe as estatísticas do uso da memória virtual

**-------------------------------------------------------------------------------------------------------------**

**systemd:**  Ele é responsável por iniciar, parar e gerenciar serviços do sistema durante a inicialização e o tempo de execução.

    Funções principais:

    Inicialização de serviços durante a inicialização do sistema.

    Gerenciamento de serviços em execução

    Controle de dependência entre serviços

    Monitoramento e inicialização de serviço com falham

    Gestão de unidade de sistema (Arquivos de configuração que descrevem serviços, montagem e dispositivos)

**-------------------------------------------------------------------------------------------------------------**

**Journalctl:** É uma ferramenta que faz parte do systemd , utilizada para verificar registros armazenados no systemd  “Systemd Journal”

    Funções principais:

    -	Permite pesquisa e visualização de logs do sistema incluindo     mensagens de inicialização, logs do kernel, serviços e muito mais.

    -	Oferece recursos de filtragem e formatação além de ajudar na análise e desenvolvimento do sistema.


**-------------------------------------------------------------------------------------------------------------**

## Comandos de Redes#

**ip [a,route] show:** lista as interfaces de rede

    route: Lista as rotas de redes atuais do sistema

    a: Mostra link e addr juntos

    -c -br ad:Mostra as interfaces mais detalhados

**ping [-c]:** Verifica a conectividade entre dois computadores

    C: Diz quantidades de pacotes

route,netstat -r, ip route show :Lista as rotas de redes atuais do sistema

**tcpdump[-i,-e,-w,-n,-p,-c,-]:** Mostra o tráfego de rede em tempo real

    i: Escolhe a interface

    e: Exibe o cabeçalho ethernet completo

    w: Grava em um arquivo

    n: Não resolve o nome de host

    p: Captura apenas tráfegos destinado a máquina

    c: Define quantos pacotes deve capturar

**traceroute ip:** Rastreia o endereço ip

**arp:** Lista os dispositivos conectados na sua rede

**nslookup:** resolução de nome	

**sudo /etc/init.d/networking restart:** Reinicia a interface

**dig:** Resolução de nome (DNS) detalhada

**ss[-t, -u, -s, -a,-n,-r,,-e,-p,-4,-6,-K]:** Mostrar os sockettes(terminal de comunicação)

    t: apenas tcp

    u: apenas udp

    s: Resumo dos sockets

    a: Lista todos os sockets

    n: mostra a porta e o ip

    r: mostar ip e porta por nome de serviço

    e: mostra informações detalhadas dos sockets

    p: mostra o processo associado ao ao socket

    4: filtra apenas ipv4

    6: filtra apenas ipv6

    K: força o fechamento dos sockets

**sudo ifup nome:** Sobe a interface

**sudo ifdown nome:** Derruba a interface

**nmcli:** usar para criar, exibir, editar, excluir, ativar e desativar conexões de rede, bem como controlar e exibir o status do dispositivo de rede

## Informações de rede

en: Ethernet

ib: InfiniBand

sl: Serial line IP (slip)

wl: Rede de área local sem fio (WLAN)

ww: Rede de longa distância sem fio (WWAN)

Placa de rede loopback: É um tipo especial de interface que permite fazer conexões com você mesmo.

MTU: É o tamanho, em bytes, do maior pacote permissível que pode ser passado pela conexão.

## Diretórios importantes 

Armazena o nome da máquina

    /etc/hostname

Mapear ip para nome

    /etc/hosts

Aponta o servidor dns / Configurações com resolução de nome (DNS)

    /etc/resolv.conf

Search: Especifica onde vai proucurar

Configurar interfaces da máquina

    /etc/network/interfaces

**-------------------------------------------------------------------------------------------------------------**

## Comandos de Partições

**fdisk[-l]:** Criar partições em mbr

    l : Lista as partições existentes no disco atual

**df[-a,-i,-m,-t,-T,-x]:** Mostra o espaço livre e ocupado das partições

    a: Lista os sistemas de arquivo com zero blocos

    i: Informar os inode

    m: Lista em MB

    `t (tipo): Mostra o tipo específico de sistema de arquivo

    T: Exibe o tipo de sistemas listado

    x: Especificar o tipo de sistema que não vai aparecer

**du[-a,-c,-h]:** Mostra o espaço usados pelos diretórios

    a: Mostra os espaços usados pelos arquivos

    c: Mostra o total de espaço usado

    h: Exibe formato de tamanho compreensivo ao ser humano

mount: Associar um sistema de arquivos a um diretório específico

gdisk: Cria partições em gpt

mkfs: Cria um sistema de arquivo no dispositivo, em uma partição do HD

fsck: Deve ser utilizado em sistemas de arquivos desmontados. Ele verifica o sistema de arquivo para recuperar dados perdidos ou danificados.
