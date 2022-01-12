# Django Channels practice

This project is intended to help me explore the whole functionality of Django Channels before implementing it in other projects.


## Introduction

### Tartarugas até lá embaixo

Django Channels permite suporte para tarefas assíncronas e outros protocolos como WebSockets, MQTT, chatbots e etc. Ele não exclúi o uso de código síncrono ou HTTP, mas além disso adiciona integração com autenticação, sessões e mais.

### Escopos e Eventos

Um escopo é um conjunto de detalhes sobre uma conexão recebida.

Eventos são interações do usuário. Por exemplo, uma requisição HTTP ou um frame de WebSockets.

Para lidar com os eventos de uma conexão, é necessário escrever uma instância de uma applicação ASGI. Django Channels já faz isso para nós por meio dos Consumers.

### O que é um Consumer?

Um Consumer é um pedaço de código Channel que consome eventos. Diferente das views de Django, eles possuem longa duração, ou como foi dito, pela duração de um escopo.

Em Python, um Consumer pode ser uma classe, e seus métodos representam cada evento.

Podemos rodar operações síncronas como ao chamar a ORM Django. Porém também podemos usar funções assíncronas.

### Roteamento e Múltiplos Protocolos

É possível combinar várias rotas do seu web app com diferentes aplicativos ASGI, desta forma combinando vários protocolos diferentes.

### Comunicação Cross-Process

Quando projetos ficam grandes, surge a necessidade de se instancias de aplicações diferentes comunicarem entre si. Por exemplo, se você está fazendo uma sala de chat, quando uma instancia de uma aplicação receber uma mensagem, ela precisa distruir isso para outras instâncias que representam as pessoas na sala de chat.

### Integração com Django

Há suporte para auth e sessions.
