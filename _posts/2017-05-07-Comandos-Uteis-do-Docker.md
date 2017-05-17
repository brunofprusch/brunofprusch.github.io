---
layout: post
title: Comandos Úteis do Docker
excerpt: "Comandos Úteis do Docker"
modified: 2016-05-07
tags: [intro, beginner, jekyll, tutorial]
comments: true
image:
  feature: docker-logo.png
---

Este post não tem o objetivo de explicar o que é Docker e como ele funciona, é apenas um post contendo comandos úteis muito utilizados ao se trabalhar com o Docker.

##### Comandos de manipulação de imagens


- Listar as images existente localmente ou no host que está configurado:

```
 docker images
```

- Remover uma imagem:

```bash
 docker rmi <id da imagem>
```

- Remover todas as images:

```bash
 docker rmi $(docker images -q)
```


- Contruir uma imagem a partir de um Dockerfile

```bash
 docker build -t <nome_da_imagem> <caminho_para_dockerfile>

	 Exemplo:
	 	docker build -t test .
```


##### Comandos de manipulação de containers

- Listar os containers em execução:

```bash
 docker ps
```


- Remover um container:

 	docker rm -f <id do container>

 		* O -f é para forçar a remoção

 
 -  Remover todos os containers em execução:

	docker rm -f $(docker ps -qa)

 
 - Executando um container:

	docker run <nome da imagem>
 

 -  Executando um container já passando um comando para uma determinada ação, como por exemplo acessar o terminal:

	docker run -it <nome da imagem> <comando>

		Exemplo: docker run -it ubuntu /bin/bash

 
 - Executando um container mapeando porta:

 	docker run -it -p <portas> <nome da imagem>

 		Exemplo: docker run -it -p 8080:80 ubuntu


 - Executando um container especificando a memória:

 	docker run -it -m <tamanho da memória> <nome da imagem> <comando>

 		Exemplo: docker run -ti -m 512M ubuntu /bin/bash

 		Obeservação: Quando não é especificado o tamanho da memória, é utilizado o total de memória do host.


 - Executando um container especificando a CPU:

 	docker run -ti --cpu-shares <cpu> <nome da imagem> <comando>

 		Exemplo: docker run -ti --cpu-shares 1024 ubutu /bin/bash

 		Observação: Explicar a questão de proporção.


 - Executando comando dentro do container sem precisar entrar no mesmo:

 	docker exec -it <id do container> <comando>

 		Exemplo: docker exec bger54thwrgf4 ps -ef


 - Obter informações do container em execução:

 		docker inspect <id do container>


 - Verificar o quanto um container está consumindo, rede, memória, cpu:

 		docker stats <id do container>


 - Manipular cpu, memória, i/o etc... sem precisar derrubar o container em execução:

 	Observação: O comando docker update está disponível a partir da versão 1.10 do docker.

 	
 	- Manipulando memória:

	 		docker update -m <tamanho da memória> <id do container>

	 			Exemplo: docker update -m 256M 98iujdh65fdyb

	 
	 - Manipulando CPU:

	 		docker update --cpu-shares <tamanho do cpu> <id do container>

	 			Exemplo: docker update --cpu-shares 512 98iujdh65fdyb






 #### referenre a criação de imagem com Docker file:

 	- Um docker file por diretório somente, pois na criação da imagem se aponta para o diretório que consequentemente só tem um Dockerfile dentro.

 	- Legal sempre colocar no Dockerfile o MAINTAINER, ou seja, quem criou o Dockerfile, o email por exemplo.

 	- 











