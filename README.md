# Projeto de Bloco: Arquitetura de Infraestrutura de Aplicações

### Apresentação:
- Será realizada a execução de uma aplicação Wordpress através de uma playbook Ansible. A aplicação é composta por containers Docker em um host vSphere.

## Implementação do Ansible

![

## Implementação do Docker

![Docker Logo](https://github.com/maa-targino/Playbook-Docker/blob/main/docker-logo.png)  

### Instalação do Docker no Ubuntu:

- **Neste passo-a-passo vamos instalar o Docker em uma máquina Ubuntu 20.04.  
Para realizar a instalação na sua máquina, copie os comandos e execute-os no seu terminal.**

1. Remova as possíveis versões antigas do Docker já instaladas:  
> ```
> sudo apt-get remove docker docker-engine docker.io
> ```

2. Atualize o gerenciador de pacotes:  
> ```
> sudo apt-get update  
> ```

3. Adicione a chave oficial do repositório do Docker ao sistema:  
> ```
> curl -fsSL https&#xfeff;://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -  
> ```

4. Adicione o repositório do Docker ao APT:
> ```
> sudo add-apt-repository \  
>   "deb [arch=amd64] https&#xfeff;://download.docker.com/linux/ubuntu \  
>    $(lsb_release -cs) \  
>    stable"
> ```

5. Atualize o gerenciador de pacotes novamente para ter acesso aos novos pacotes do repositório do Docker:
> ```
> sudo apt-get update
> ```

6. Instale o pacote **docker-ce**:
> ```
> sudo apt-get install docker-ce
> ```

7. Para verificar se o Docker foi instalado corretamente, verifique sua versão:
> ```
> sudo docker --version
> ```

## 
