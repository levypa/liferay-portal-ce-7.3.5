# liferay-portal-ce-7.3.5

# Instalação do Docker no Ubuntu 20.04 (containers)

[Install Docker Engine on Ubuntu](https://docs.docker.com/engine/install/ubuntu/)

Um servidor Ubuntu 20.04 configurado conforme o Guia de configuração inicial de servidor do Ubuntu 20.04, incluindo um usuário sudo não root e um firewall. Uma conta no [Docker Hub](https://hub.docker.com/) se você deseja criar suas próprias imagens e enviá-las para o Docker Hub

## Passo 01: Instalação do Docker e Docker Compose

** Docker **

    ``` sudo apt update ```

    ``` sudo apt install apt-transport-https ca-certificates curl software-properties-common ```

    ``` curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - ```

    ``` sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable" ```

    ``` sudo apt update ```

    ``` apt-cache policy docker-ce ```

    ``` sudo apt install docker-ce ```

    ``` apt-get install docker-compose ```

## Passo 02: Comando básicos
### 

    ``` docker ```

    ``` docker --version ```

    ``` systemctl status docker ```

    ``` docker docker-subcommand --help ```

    ``` docker info ````

## Passo 03: namespaces
### isolamento de processos
    **Exemplo:** 
            - Pid:
            - User:
            - Network:

## Passo 04: cgrups
### controla os recursos do
    **Exemplo:**

## Passo 05: 
### Overlay File System
    **Exemplo:**

## Passo 06: Baixa e executa uma imagem de teste do Doc

    ``` docker run hello-world ````

## Passo 07: Baixar e executar uma imagem do bash do ubuntu

    ``` docker run -it ubuntu bash ```     

    ``` docker run ubuntu /bin/bash ```  

    ** Iniciarndo um serviço com o nginx: **

    ``` docker run -d -p 80:80 --name nginx-docker nginx ```

## Passo 08: Manipular imagens e containers docker

    ** Listar imagens docker **

    ``` docker images ```

    ** Parar container docker **

    ``` docker stop nginx-docker ```

    ** Remover container docker **

    ``` docker rm nginx-docker ```

    ** Remover imagem docker **

    ``` docker rmi nginx ```

    ** Remover todas as imagens docker que estão ociosas

    ``` docker system prune ```

## Passo 08: Instalar imagens e container do Docker Hub

 ** Docker Compose **

## Passo 09: Baixar, instalar e iniciar umagens e seus os containers docker

    ``` docker-compose up -d ```

** Parar o container Docker **

    ``` docker-compose stop ```

** Iniciar o container Docker **

    ``` docker-compose start ```

** Parar e remover containers da máquina **

    ``` docker-compose down ```

## Passo 10: Monitorar recursos dos containers

    ``` docker stats ```


## Passo 11: Manipular imagens do Dockerfile (imagem local de NODE, como exemplo.)

    ``` docker build . ```

    ``` docker images ```

    ``` docker run -d -p 3000:3000 -d node-docker ```

    ``` docker stop node-docker ```

    ``` docker build -f node-docker-image ```

    ``` docker run -d -p 3001:3001 --name node-docker2 node-docker-image ```

    ``` docker stop node-docker2 ```

    ``` docker rmi node-docker2 ```

    ``` docker system prune ```


## Passo 12: Converter aquivos para uma imagem local

    ``` docker build -t levypa/liferay-ce-portal-7.3.5:latest . ```

    ``` docker build -t levypa/mysql-liferay-ce-portal-7.3.5:latest . ```

## Passo 13: Criar imagem local (dentro do diretório do arquivo Dockerfile)

    ``` docker push levypa:mysql-liferay-ce-portal-7.3.5 ```

    ``` docker push levypa:liferay-ce-portal-7.3.5 ```

## Passo 14: Subir imagem para Docker Hub (dentro do diretório do arquivo do Dockerfile)

    ``` docker login ```

    ``` docker push levypa/mysql-liferay-ce-portal-7.3.5 ```

    ``` docker push levypa/liferay-ce-portal-7.3.5 ```

## Passo 15: Monitorar containers com parâmetros especiais

    ``` docker stats $(docker ps|grep -v "NAMES"|awk '{ print $NF }'|tr "\n" " ") ```

# Passo 10 - Executar uma imagem e atribuir parametros de configuração

    ``` docker run -it --rm -p 8080:80 -p 443:443 --name php8site -v "$PWD":/var/www/html php8 ```


