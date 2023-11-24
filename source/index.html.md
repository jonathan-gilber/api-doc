---
title: API Reference

language_tabs: # must be one of https://github.com/rouge-ruby/rouge/wiki/List-of-supported-languages-and-lexers
  - javascript

toc_footers:
  - <span><b>Equipe Midas</b></span>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Kittn API
---

# Introdução

Bem-vindo à documentação da API Midas. Aqui você encontrará informações detalhadas sobre todos os endpoints disponíveis, explicando suas funcionalidades, métodos HTTP e fornecendo trechos de código exemplificando seu uso.

### Plataforma Midas

`http://midas.accenture.com/`

# Autenticação

Para assegurar a proteção adequada, é essencial que os usuários se conectem à VPN AI-Vnet (Rede Virtual de Inteligência Artificial) ao realizar requisições na plataforma Midas. A VPN AI-Vnet representa uma camada adicional de segurança, garantindo uma comunicação segura entre o usuário e os endpoints, reforçando a proteção dos dados durante a transmissão. Certifique-se de estar conectado para ter acesso às requisições com segurança.

<aside class="success">
Lembre-se, não é possível consultar dados sem estar autenticado e conectado à VPN
</aside>

# Auth

## Signup

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Ao utilizar este endpoint, os usuários podem realizar o processo de cadastro em nossa plataforma, fornecendo as informações necessárias para criação de suas contas.

### Requisição HTTP

`POST /auth/signup`

### Request Body

{
"username": "string",
"password": "string"
}

## Signin

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Ao utilizar este endpoint, os usuários podem realizar o processo de autenticação, fornecendo suas credenciais previamente cadastradas. Uma vez autenticados com sucesso, receberão um token de acesso, permitindo a utilização segura dos recursos protegidos pela plataforma.

### Requisição HTTP

`POST /auth/signin`

### Request Body

{
"username": "string",
"password": "string"
}

## Me

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "deleted": ":("
}
```

Ao realizar uma requisição para o endpoint "Me", a plataforma responderá com informações sobre o estado de autenticação do usuário.

### Requisição HTTP

`GET /auth/me`

# Fornecedores

## Digitalizados

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Esse endpoint ao ser executado retorna uma lista com o nome de todas as fornecedoras e a quantidade de documentos específicos de cada uma delas, podendo ser PPI, FCU ou SCI, junto ao numero da soma deles.

### Requisição HTTP

`GET /fornecedor/documentos/digitalizados`

## Faltantes

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Retorna uma lista com todas as torreiras, e quantos documentos de cada tipo ainda não foram digitalizados

### Requisição HTTP

`GET /fornecedor/documentos/faltantes`

## Total

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "deleted": ":("
}
```

Retorna uma lista com o nome de todas as torreiras e a quantidade total de sites de cada uma

### Requisição HTTP

`GET /fornecedor/sites/total`

## FCU

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

### Requisição HTTP

`GET /fornecedor/sites/status/by/fcu`

# Portfólios

## Info

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Através dos parâmetros fornecidos retorna informações sobre um determinado portfolio.

### Requisição HTTP

`GET /portfolio/info/{portfolio}`

### Parâmetros de URL

| Parâmetro | Descrição            | Exemplo           |
| --------- | -------------------- | ----------------- |
| portfolio | Nome de um portfolio | ALFA - COLLO 2015 |

## Listar

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

lista os portfólios e exibe algumas informações sobre cada um.

### Requisição HTTP

`GET /portfolio/listar`

## Sites

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "deleted": ":("
}
```

Fornece informações sobre os sites pertencentes ao portfólio informado no parâmetro.

### Requisição HTTP

`GET /portfolio/sites/{portfolio}`

### Parâmetros de URL

| Parâmetro | Descrição            | Exemplo           |
| --------- | -------------------- | ----------------- |
| portfolio | Nome de um portfolio | ALFA - COLLO 2015 |

## Save Config

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Recebe um JSON de configuração para cálculo de compliace com base em PPIs para o portfólio e salva a atualização no banco de dados.

### Requisição HTTP

`POST /portfolio/save/config`

## Config

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Retorna o JSON de configuração atual do portfólio passado no parâmetro

### Requisição HTTP

`GET /portfolio/config/{portfolio}`

### Parâmetros de URL

| Parâmetro | Descrição            | Exemplo           |
| --------- | -------------------- | ----------------- |
| portfolio | Nome de um portfolio | ALFA - COLLO 2015 |

## Config File

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Recebe um arquivo xlsx com a configuração do contrato para cálculo do compliance com base na FCU.

### Requisição HTTP

`POST /portfolio/config/upload`

### Request Body

"files": "file.xlsx"<br>

## Validacao File

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Gera uma validação com base na configuração atual.

### Requisição HTTP

`POST /portfolio/validacao/upload`

### Request Body

"files": "file.xlsx"

## Regras

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Exibe as regras do portfólio informado por parâmetro.

### Requisição HTTP

`GET /portfolio/regras/{portfolio}`

### Parâmetros de URL

| Parâmetro | Descrição            | Exemplo           |
| --------- | -------------------- | ----------------- |
| portfolio | Nome de um portfolio | ALFA - COLLO 2015 |

## By Site

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

retorna uma lista de sites e suas informações categorizados por portfólio.

### Requisição HTTP

`GET /portfolio/by/site`

## Report

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

retorna uma lista de portfólios e suas informações.

### Requisição HTTP

`GET /portfolio/report`

## Normalizacao Report

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Utilizado para criar de-para da nomenclatura do portfólio e fornecedores para padronizar os nomes na base.

### Requisição HTTP

`GET /portfolio/normalizacao`

<aside class="warning">
Endpoint descontinuado temporariamente
</aside>

## AEV History

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Retorna o histórico de AEV do portfólio, medindo a evolução em cada SCI dos contratos.

### Requisição HTTP

`GET /portfolio/aev/historico/{portfolio}`

### Parâmetros de URL

| Parâmetro | Descrição            | Exemplo           |
| --------- | -------------------- | ----------------- |
| portfolio | Nome de um portfolio | ALFA - COLLO 2015 |

# Sites

## Upload Adicionais

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Faz o upload de um arquivo xlsx com registro de sites que irão receber valores adicionais ao calcular o compliance, o mesmo arquivo serve para adicionar valores e/ou remover.

### Requisição HTTP

`POST /site/upload/adicionais`

### Request Body

"file": "file.xlsx"

## Adicionais

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Lista os valores dos sites que possuem adicionais.

### Requisição HTTP

`GET /site/adicionais`

## Apiatc Report

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "deleted": ":("
}
```

Retorna um gráfico dos dados da API da ATC.

### Requisição HTTP

`GET /site/apiatc`

<aside class="warning">
Endpoint descontinuado temporariamente
</aside>

## Site Status

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Informa de forma agrupada por fornecedor a quantidade de sites com documentos completos e incompletos.

### Requisição HTTP

`GET /site/status/by/fornecedor/complete`

## Lista

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Faz uma listagem de todos os contratos com informações do fornecedor portfólio e a quantidade de cada tipo de documentos digitalizados.

### Requisição HTTP

`GET /site/lista`

## Info

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Fornecendo o número de contrato como parâmetro, é retornado informações sobre o site especificado.

### Requisição HTTP

`GET /site/info/{contrato}`

### Parâmetros de URL

| Parâmetro | Descrição                     | Exemplo       |
| --------- | ----------------------------- | ------------- |
| contrato  | Número do contrato de um site | 3100000011005 |

## Arquivos

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Fornecendo o número de contrato como parâmetro, é retornado uma lista de arquivos associados ao site especificado.

### Requisição HTTP

`GET /site/arquivos/{contrato}`

### Parâmetros de URL

| Parâmetro | Descrição                     | Exemplo       |
| --------- | ----------------------------- | ------------- |
| contrato  | Número do contrato de um site | 3100000011005 |

## Carregamento

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Fornecendo o número de contrato como parâmetro, é retornado as informações contidas nos arquivos associados ao site de forma digitalizada.

### Requisição HTTP

`GET /site/carregamento/{contrato}`

### Parâmetros de URL

| Parâmetro | Descrição                     | Exemplo       |
| --------- | ----------------------------- | ------------- |
| contrato  | Número do contrato de um site | 3100000011005 |

## Report

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Faz uma listagem de todos os sites com informações de quais documentos de cada tipo estão faltando.

### Requisição HTTP

`GET /site/report`

## Report AEV

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Retorna o relatório de AEV de cada site, informando de forma sumarizada qual o carregamento atual do site (RRU, AEV Base, AEV total com e sem CA, AEV adicional, reserva de AEV) e qual a fonte destas informações.

### Requisição HTTP

`GET /site/report/aev`

## Docs Report

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Retorna uma visão geral dos arquivos dos sites, categorizados por tipo.

### Requisição HTTP

`GET /site/report/docs`

## Report sem Docs

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Exibe a quantidade de sites de cada fornecedora que faltam documentos.

### Requisição HTTP

`GET /site/report/sem_docs`

## AEV History

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Mostra informações sobre custos medios do site e qual é a fonte deles.

### Requisição HTTP

`GET /site/aev/historico/{contrato}`

### Parâmetros de URL

| Parâmetro | Descrição                     | Exemplo       |
| --------- | ----------------------------- | ------------- |
| contrato  | Número do contrato de um site | 3100000011005 |

## Report Info

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Com base no contrato fornecido no parâmetro, traz informações específicas sobre aquele site

### Requisição HTTP

`GET /site/report/info/{contrato}`

### Parâmetros de URL

| Parâmetro | Descrição                     | Exemplo       |
| --------- | ----------------------------- | ------------- |
| contrato  | Número do contrato de um site | 3100000011005 |

# Documentos

## Lista

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Lista todos os documentos digitalizados pelo midas.

### Requisição HTTP

`GET /documento/list`

## Relatorio

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Exibe um relatório com a quantidade de cada tipo de documentos digitalizados por SCI.

### Requisição HTTP

`GET /documento/report`

## Documento

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Pesquisa pelo documento id e retorna informações do documento SAP.

### Requisição HTTP

`GET /documento/documento/{doc_id}`

### Parâmetros de URL

| Parâmetro | Descrição       | Exemplo  |
| --------- | --------------- | -------- |
| doc_id    | ID do documento | 0001bd9b |

## Update Digitalization

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Faz o upload de um arquivo e o associa à um site com base no número de contrato passado nos parâmetros.

### Requisição HTTP

`POST /documento/update/digitalization/{contrato}/{doc_type}/{doc_id}`

### Parâmetros de URL

| Parâmetro | Descrição                     | Exemplo       |
| --------- | ----------------------------- | ------------- |
| contrato  | Número do contrato de um site | 3100000011005 |
| doc_type  | Tipo do documento             | FCU           |
| doc_id    | ID do documento               | 0001bd9b      |

## FCUs

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Com base no número do contrato, fornece informações digitalizadas contidas dentro de arquivos FCU do site especificado.

### Requisição HTTP

`GET /documento/fcus/{contrato}`

### Parâmetros de URL

| Parâmetro | Descrição                     | Exemplo       |
| --------- | ----------------------------- | ------------- |
| contrato  | Número do contrato de um site | 3100000011005 |

# SAP

## Valores

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

traz valores do site contidos na base SAP baseado no número de contrato passado por parâmetro

### Requisição HTTP

`GET /sap/valores/{contrato}`

### Parâmetros de URL

| Parâmetro | Descrição                     | Exemplo       |
| --------- | ----------------------------- | ------------- |
| contrato  | Número do contrato de um site | 3100000011005 |

## Listar

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Lista as bases SAP extraídas, resume alguns de seus valores e exibe alguns de seus metadados.

### Requisição HTTP

`GET /sap/listar`

## Upload File

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Faz o upload de um arquivo de extração de base SAP.

### Requisição HTTP

`POST /sap/files`

### Request Body

"files": "file.xlsx"

## Metricas

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Retorna dados históricos de todos os arquivos do SAP que foram carregados medindo a evolução da quantidade de registros, fornecedores, portfólios, sites e valores.

### Requisição HTTP

`GET /sap/metricas`

## Upload Register

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Faz o upload do arquivo sap ao blob (external/sap).

### Requisição HTTP

`POST /sap/upload/register`

## Contrato Historico

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Retorna o histórico do custo de um contrato.

### Requisição HTTP

`GET /sap/historico/{contrato}`

### Parâmetros de URL

| Parâmetro | Descrição                     | Exemplo       |
| --------- | ----------------------------- | ------------- |
| contrato  | Número do contrato de um site | 3100000011005 |

## Portfolio Historico

> O código acima retorna uma estrutura como essa:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

Retorna o histórico do custo de um portfolio.

### Requisição HTTP

`GET /sap/historico/portfolio/{portfolio}`

### Parâmetros de URL

| Parâmetro | Descrição            | Exemplo           |
| --------- | -------------------- | ----------------- |
| portfolio | Nome de um portfolio | ALFA - COLLO 2015 |

# Faturamentos

## Lista Fornecedores

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Exibe uma lista com o nome de todas as fornecedoras.

### Requisição HTTP

`GET /billing/fornecedores/listar`

## Competencias

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Retorna uma lista com o nome das fornecedoras e informações sobre cada uma, como a competência, quantidade de sites e o valor total das categorias no faturamento.

### Requisição HTTP

`GET /billing/competencias`

## Upload File

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Recebe um arquivo de faturamento de algum fornecedor para ser processado.

### Requisição HTTP

`POST /billing/files`

### Request Body

"files": "file.xlsx"<br>
"fornecedor": "String"<br>
"referente": "MM/AAAA"

## Upload Data

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Recebe o mapa dos dados do faturamento que será usado para processar o faturamento.

### Requisição HTTP

`POST /billing/data`

## Settings

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Recebe informações de qual aba do xlsx esta o faturamento e qual o numero da linha que esta o cabeçalho.

### Requisição HTTP

`POST /billing/settings`

## Register

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Registra o faturamento na base de dados para ser usado no compliance.

### Requisição HTTP

`POST /billing/register`

# Preço

## Precos

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Baseado no número do contrato, exibe valores de custo de um site.

### Requisição HTTP

`GET /precos/contrato/{contrato}`

### Parâmetros de URL

| Parâmetro | Descrição                     | Exemplo       |
| --------- | ----------------------------- | ------------- |
| contrato  | Número do contrato de um site | 3100000011005 |

## Listar

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Exibe várias informações de valores sobre todos os sites registrados.

### Requisição HTTP

`GET /precos/listar`

## Ajustar

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Faz o ajuste do preço para o dia de hoje com base no valor inicial, índice de reajuste, mês e ano de inicio.

### Requisição HTTP

`GET /precos/ajustar/{valor}/{indice}/{mes}/{ano}`

### Parâmetros de URL

| Parâmetro | Descrição                          | Exemplo |
| --------- | ---------------------------------- | ------- |
| valor     | Valor inicial não reajustado       | 1948,27 |
| indice    | Indice de reajuste                 | IPCA    |
| mes       | Mês no qual é a plicado o reajuste | 03      |
| ano       | Ano de início do cálculo           | 2015    |

# Compliance

## Compliance

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### Requisição HTTP

`GET /compliance/compliance`

## Compliance Run

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### Requisição HTTP

`GET /compliance/compliance/run/{site_code}`

### Parâmetros de URL

| Parâmetro | Descrição                                           | Exemplo |
| --------- | --------------------------------------------------- | ------- |
| site_code | Código de identificação do site no formato UF_Sigla | SP_RGF  |

## By Fornecedor

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Apresenta uma listagem categorizada por fornecedores, juntamente com uma visão geral do cumprimento das regras, indicando o número de credores, devedores, status "ok" e o total correspondente.

### Requisição HTTP

`GET /compliance/by/fornecedor`

## Saldo Fornecedor

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Exibe uma lista categorizada pelas fornecedoras com uma visão do saldo SAP, IVA e a sua diferença de valor.

### Requisição HTTP

`GET /compliance/saldo/by/fornecedor`

## Evolution Saldo Fornecedor

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Retorna os dados para serem empregados em um gráfico que representa a evolução dos saldos ao longo do tempo.

### Requisição HTTP

`GET /compliance/evolution`

## Baseline Saldo Fornecedor

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Retorna os dados para serem utilizados em um gráfico que representa a evolução dos valores do baseline ao longo do tempo.

### Requisição HTTP

`GET /compliance/baseline`

# Carregamento

## Precos

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Retorna o relatório de carregamento.

### Requisição HTTP

`GET /carregamento/listar`

# Storage

## Get File

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Obtém um arquivo específico armazenado no blob com base no container, blob_path e blob passados por parâmetro na requisição.

### Requisição HTTP

`GET /storage/get_file/{container}/{blob_path}/{blob}`

### Parâmetros de URL

| Parâmetro | Descrição                                    | Exemplo            |
| --------- | -------------------------------------------- | ------------------ |
| container | Nome de um container dentro do azure storage | documents          |
| blob_path | Nome de um blob dentro do container          | processed          |
| blob      | Nome do arquivo desejado                     | 0001_UF_SIGLA.xlsx |

## Listar

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Lista os arquivos dentro de um blob especificado pelos parâmetros da requisição.

### Requisição HTTP

`GET /storage/list/{container}/{blob}`

### Parâmetros de URL

| Parâmetro | Descrição                                     | Exemplo   |
| --------- | --------------------------------------------- | --------- |
| container | Nome de um container dentro do azure storage  | documents |
| blob      | Nome do blob dentro do container especificado | processed |

## Carregamento

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Faz o download do relatório completo de carregamento.

### Requisição HTTP

`GET /storage/carregamento`

# GPT

## Ask

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Rota usado para fazer uma pergunta ao chat gpt midas.

### Requisição HTTP

`POST /gpt/ask`

## Ask 16k

### Requisição HTTP

`<color="red">POST</color> /gpt/ask_16k`

<aside class="notice">
Rota usada para testes
</aside>

## Ask exp

### Requisição HTTP

`POST /gpt/ask_exp`

<aside class="notice">
Rota usada para testes
</aside>

# Dashboard

## Get Access Token

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Retorna o access token da dashboard.

### Requisição HTTP

`GET /dashboard/token`

## Get ID

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Retorna o ID da dashboard do superset.

### Requisição HTTP

`GET /dashboard/id`

## Get Dashboard

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Retorna o dashboard para fazer o embedding no front.

### Requisição HTTP

`GET /dashboard/dashboard`

# ATC

## Update Sites

> O código acima retorna uma estrutura como essa:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

Retorna a data da ultima atualização dos dados da api da ATC.

### Requisição HTTP

`GET /atc/update/sites`
