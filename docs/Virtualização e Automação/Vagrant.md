# **Vagrant**

Trabalha em conjunto com o docker, Virtual Box, entre outros

1º - O comando 2º Cria um arquivo vagrantfile e nele ocorre as configurações

* Ao abrir o arquivo a primera etapa e sua versão que por padrão vem última ("2")
[![Versão do vagrabt](https://i.im.ge/2023/12/15/EZgCsr.Versao-do-vagrabt.png)](https://im.ge/i/EZgCsr)

* Configurando qual imagem vamos usar, como podemos ver nesse caso usamos "debian 12"
[![Debian](https://i.im.ge/2023/12/15/EZVBbq.Debian.png)](https://im.ge/i/EZVBbq) 
você pode encontra o nome das vms aqui: [VMS](https://app.vagrantup.com/boxes/search)

* Verifica se tem uma imgem mais atualizada, nesse caso esta desativado
[![Verifiq-update](https://i.im.ge/2023/12/15/EZgt3f.Verifiq-update.png)](https://im.ge/i/EZgt3f)

* Faz o redirecionamento de portas da vm para a máquina real
[![Redirecionamento de porta](https://i.im.ge/2023/12/15/EZgPU1.Redirecionamento-de-porta.png)](https://im.ge/i/EZgPU1)


* Redireciona o tráfego de porta para um ip específico, nesse caso e localmente, ou seja, própria máquina
[![Redirec de portas para um ip](https://i.im.ge/2023/12/15/EZgNTP.Redirec-de-portas-para-um-ip.png)](https://im.ge/i/EZgNTP)

*  Configura uma ip fixo na rede privada do vagrant
[![Rede privada com host-only](https://i.im.ge/2023/12/15/EZg0tD.Rede-privada-com-host-only.png)](https://im.ge/i/EZg0tD)


*  A interface de rede se torna modo bridge, recebendo um ip do roteador
[![public](https://i.im.ge/2023/12/18/En0v88.public.png)](https://im.ge/i/En0v88)

*  Compartilha arquivos do host com o vm
[![Shere with guest](https://i.im.ge/2023/12/15/EZg5k4.Shere-with-guest.png)](https://im.ge/i/EZg5k4)

*  True para ativa interface gráfica e False para desativar 
[![Define o virtualizador](https://i.im.ge/2023/12/15/EZgmjq.Define-o-virtualizador.png)](https://im.ge/i/EZgmjq)

* Determina a quantidade de RAM que vai usar               
[![Define a quatida de memória](https://i.im.ge/2023/12/15/EZgjFC.Define-a-quatida-de-memoria.png)](https://im.ge/i/EZgjFC)

* Os comando que serão usado ao iniciar a vm
[![Comandos](https://i.im.ge/2023/12/15/EZgwRp.Comandos.png)](https://im.ge/i/EZgwRp)


2º - Criar uma vm com o (SO) escolhido
    
    vagrant init nome_do_SO

            OU

    (vagrant init) e editar o arquivo vagrantfile

3º - Sobe a VM

    vagrant up nome da VM

4º - Loga na VM

    vagrant ssh nome

5º - Desliga a VM   
    
    vagrant halt  

6º - Salva o estado da VM e suspende

    vagrant suspend

7º - retira da suspensão

    vagrant resume nome_do_vm

8º - Destrói a VM

    vagrant destroy

9º -  Defino o hypervisor

    vagrant up --provider=docker |docker|
    vagrant up --provider=virtualbox |box|



