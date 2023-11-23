# **Vagrant**

Trabalha em conjunto com o docker, Virtual Box, entre outros

1º - O comando 2º Cria um arquivo vagrantfile e nele ocorre as configurações



2º - Criar uma vm com o (SO) escolhido
    
    vagrant init nome_do_SO

3º - Sobe a VM

    vagrant up nome da VM

4º - Loga na VM

    vagrant ssh nome

5º - Desliga a VM   
    
    vagrant halt  

6º - Salva o estado da VM e suspende

    vagrant suspend

7º - retira da suspensão

    vagrant resume nome do vm

8º - Destrói a VM

    vagrant destroy

9º -  Defino o docker como hypervisor

    vagrant up --provider=docker


https://app.vagrantup.com/boxes/search : Cloud de VMs
