# Projeto de Bloco: Arquitetura de Infraestrutura de Aplicações

### Apresentação:
- Será realizada a execução de uma aplicação Wordpress através de uma playbook Ansible. A aplicação é composta por containers Docker.

## Implementação do Docker  

# ![Docker Logo](https://github.com/maa-targino/Playbook-Docker/blob/main/docker-logo.png)  
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

4. Adicione o repositório do Docker ao **apt**:
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

## Implementação do Ansible  
# ![Ansible Logo](https://github.com/maa-targino/Playbook-Docker/blob/main/ansible.png)

### Instalação do servidor de SSH:

- **Nesta etapa precisaremos primeiro fazer a instalação do servidor de SSH, que é necessário para o uso do Ansible.**

1. Faça a instalação do servidor de SSH:
> ````
> sudo apt-get install openssh-server
> ````

2. Altere as permissões de root para o acesso do servidor de SSH:
> ````
> sudo gedit etc/ssh/sshd_config
> ````

3. Reinicie o servidor de SSH:
> ````
> service ssh restart
> ````

4. Gere uma nova chave SSH:
> ````
> ssh-keygen
> ````

5. Salve a nova chave SSH com o seguinte comando:
> ````
> cp -p ~/.ssh/id_rsa.pub ~/.ssh/authorized_keys
> ````

### Instalação do Ansible:

- **Neste passo-a-passo vamos fazer a instalação do Ansible.**

1. Execute o seguinte comando para criar um novo repositório Ansible:  
Depois, tecle *ENTER* sempre que o sistema solicitar.
> ````
> sudo apt-add-repository ppa:ansible/ansible
> ````

3. Faça a atualização do gerenciador de pacotes:
> ````
> sudo apt-get update
> ````

#### 2.2.4 Faça a instalação do Ansible:

>user@ubuntu:~$ sudo apt-get install ansible

#### 2.2.5 Verifique a versão e confirme se o Ansible foi instalado corretamente:

>user@ubuntu:~$ ansible --version


### Implementação da playbook Ansible:

- Neste passo-a-passo iremos criar o diretório e os arquivos necessários para a implementação da playbook Ansible.

1. Crie um novo diretório para a sua playbook:
> ````
> mkdir folder-name
> ````

2. Vá para o caminho da pasta:

> ````
> cd folder-name
> ````

3. Crie o arquivo hosts:
> ````
> sudo gedit hosts
> 

4. Insira as seguintes informações no arquivo hosts:
> ````
> [header-name]
> 127.0.0.1
> ````

5. Crie o arquivo playbook.yml:
> ````
> sudo gedit playbook.yml
> ````

6. Insira as seguintes informações no arquivo playbook.yml:
> ````
> ---
> - hosts: header-name
>   remote_user: username
>   become: yes
>   tasks: 
>      - name: "Execute the MySQL container"
>        docker_container:
>          name: database
>          image: mysql:5.7
>          env: 
>            MYSQL_ROOT_PASSWORD: your-password
>      - name: "Execute the WordPress container"
>        docker_container:
>           name: wordpress
>           image: wordpress
> ````

. Execute a playbook com o seguinte comando:

> ````
> sudo ansible-playbook -i hosts playbook.yml
> ````

#### 4.1.3 Ao iniciar a execução da playbook você verá algo semelhante a isso:

#### 4.1.4 Ao término da execução da playbook, caso tenha sido bem sucedida você verá o seguinte:

### 4.2 Acesse o Wordpress

#### 4.2.1 Abra o seu browser e acesse o IP do localhost:

> 127.0.0.1/

#### 4.2.2 Você verá uma tela semelhante a essa:
