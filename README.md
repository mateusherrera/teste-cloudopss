# Teste Cloudopss Solution

## Container Python

###### Build da imagem

Criando imagem Python com Dockerfile
1. Entre na pasta python com o terminal.
2. Faça o build da imagem.

  `docker build -t "Nome para imagem (Sem aspas)" .`

###### Executando a imagem

Com a imagem criada basta rodar o comando abaixo para rodá-la em modo interativo, com conectividade na porta local 8080.

  `docker run -it -p 8080:8080 "Nome para imagem (Sem aspas)" bash`

###### Parar e excluir container/imagem

Para pegar o id do container

  `docker ps -qa`

Copie o id do container que deseja parar ou excluir

Para parar a execução do container

  `docker stop "id copiado (Sem aspas)"`
  
Para excluir o container parado:

  `docker rm "id copiado (Sem aspas)"`

Para excluir a imagem

  `docker rmi "Nome para imagem (Sem aspas)"`

## Docker-compose de container Python com mysql

###### Criando volume docker

Primeiramente crie o volume gerenciado pelo docker:

  `docker volume create volumecopss`

###### Executando docker-compose com python e mysql

Para executar o docker-compose do container python com o mysql, vá entre na pasta ymls pelo terminal e use o comando abaixo, já iniciará em modo interativo.
Para isso a imagem do Dockerfile python anterior deve ser criada com o nome: `mateusherrera/copsspython:1.0` ou modificar o esse valor `image:` no arquivo docker-compose.yml


  `docker-compose up`


A conexão com a porta local é `8080:8080` e o container python e o mysql estão na network `compose-bridge-opss`.

###### Caso queira excluir o volume criado

Rode o comando:

  `docker volume rm volumecopss`