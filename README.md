# Implementação do Docker

![Docker Logo](https://github.com/maa-targino/Playbook-Docker/blob/main/docker-logo.png)  

## Instalação do Docker no Ubuntu:

#### Neste passo-a-passo vamos instalar o Docker em uma máquina Ubuntu 64 bits. Para realizar a instalação na sua máquina Ubuntu siga os comandos abaixo e execute-os no seu terminal.

1. Remova as possíveis versões antigas do Docker já instaladas:  
> sudo apt-get remove docker docker-engine docker.io  

2. Atualize o gerenciador de pacotes:  
> sudo apt-get update

3. Adicione a chave oficial do repositório do Docker ao sistema:  
> curl -fsSL https&#xfeff;://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -  

4. Adicione o repositório do Docker ao APT:
> sudo add-apt-repository \  
   "deb [arch=amd64] https&#xfeff;://download.docker.com/linux/ubuntu \  
   $(lsb_release -cs) \  
   stable"  
