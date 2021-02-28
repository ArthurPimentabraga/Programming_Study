---
title: Web Architecture and HTTP
author: Arthur P. Braga
---

## General Architecture Web

O ambiente cliente faz uma requisição para o servidor (podendo estar no seu próprio computador, XAMPP... ou não) que o entrega uma resposta, como por exemplo uma página web;

<img src="../imgs/AmbienteServidor.png" alt="AmbienteServidor"/>

- **Servidor Web ->** é o software que faz toda a orquestração da interação do usuário com os recursos que estão no *ambiente servidor*, sendo eles o servidor de arquivos(html, css, js...), o *servidor de aplicações*, ou seja, todo seu back end, *servidores de serviços*(APIs) e o servidor de banco de dados;

#### Web server functions

- Atender requisições HTTP e responder;
- Gerenciar multiplos site (IPs, domínios, Portas...) e os arquivos dos mesmos;
- Integração dos arquivos do site com os mecanismos de script (PHP, Python...);
- Autenticar os usuários das requisições, pondendo ser feito pelo próprio protocolo HTTP, quanto por intregração de servidores de autenticação (LDAP, Microsoft Active Directory...);
- Implementar a cripitografia na comunicação HTTPS - TSL/SSL, ou seja, é responsabilidade do servidor fazer as "negociações" das certificações com o browser em uma requisição HTTPS;
- Cache de recursos;
- Auditoria, ou seja, o servidor armazena todas as requisições e interações feitas para uma possível futura auditoria;

---

## URI, URL e URN

#### URI -> Uniform Resource Identifier

É um padrão de endereçamento, um indentificador de recursos¹ disponíveis na rede. Que engloba a **URL** e a **URN**.

#### URL -> Uniform Resource Locator

Engloba: Esquema, User:pass, Host, Porta, Caminho ou Path, Query e Fragmento.

esquema://user:pass@host:porta/caminho?query#fragmento

Ex: https://localhost:8080/index.html?id=15

- Esquema: https (protocolo http) -> podendo ser FTP², telnet...;
- Host: localhost -> outro exemplo poderia ser www.google.com;
- Porta:  8080;
- Caminho: index.html;
- Query: id=15 -> neste caso está passando o valor do parâmetro id;

Ex2: ftp://user:pass@server.net:21/documentos/arquivo.zip

#### URN -> Uniform Resource Name

 A diferença da *URN* para a *URL* é que se identifica somente o recurso desejado, sem especificar a localização (página, site...).

urn: <NID> : <NSS>

esquema:namespace_indetifier:namespace_specific_string

- NID -> Namespace Identifier
- NSS -> Namespace Specific String

Ex: urn:isbn:978-1-491-91866-1

#### Referências

*1 -> Pode ser uma página, img, server...*

*2 -> Protocolo de transferência de arquivos de um modo interativo.*

*Obs: DNS -> Para que não tenhamos que acessar os sites informando diretamente o IP no host, o DNS (Domain Name System) é responsável por traduzir e localizar o IP através de um "nome", através do endereço dos sites em que estamos acostumados. Ex: www.gmail.com;* 

---

## Protocol HTTP - Hypertext Transfer Protocol

#### What is

É um dos protocolos de transferência do modelo TCP/IP (UDP no caso do HTTP v3) que permite a transferência de dados da internet. Onde o ambiente cliente, através de uma requisição, recebe as informações desejadas (a resposta), em formato de hipertextos, pelo servidor. 

#### Methods

GET, POST, DELETE, PATCH, PUT...

#### Notes

No corpo da resposta é informado o "code status", por exemplo o 404, 200...

E existe um padrão para os propósitos: https://http.cat/

| Código | Propósito        |
|:------:|:----------------:|
| 1xx    | informacional    |
| 2xx    | Sucesso          |
| 3xx    | Redirecionamento |
| 4xx    | Erro no cliente  |
| 5xx    | Erro no servidor |