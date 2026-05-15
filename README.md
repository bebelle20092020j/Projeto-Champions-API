# Champions API

API desenvolvida no bootcamp da DIO para praticar backend com Node.js, Express e TypeScript. O projeto trabalha com jogadores e clubes de futebol, permitindo listar, buscar, criar, atualizar e remover jogadores, além de consultar clubes cadastrados.

## Sobre o projeto

A proposta desta API é simular uma base simples inspirada em jogadores e clubes da Champions League. O foco principal do projeto é treinar a criação de rotas REST, separação de responsabilidades e padronização de respostas HTTP.

Os jogadores ficam em memória durante a execução da aplicação. Já os clubes são lidos a partir de um arquivo JSON local.

## Funcionalidades

- Listar jogadores.
- Buscar jogador por ID.
- Filtrar jogadores por nome, clube, nacionalidade ou posição.
- Cadastrar um novo jogador.
- Atualizar estatísticas de um jogador.
- Remover jogador.
- Listar clubes.
- Buscar clube por ID.
- Verificar se a API está online.
- Retornar erros de forma padronizada.

## Tecnologias utilizadas

- Node.js
- TypeScript
- Express
- CORS
- TSX
- TSUP

## Como rodar

Instale as dependências:

```bash
npm install
```

Crie ou mantenha um arquivo `.env` na raiz do projeto:

```env
PORT=3333
```

Execute em desenvolvimento:

```bash
npm run start:dev
```

A API ficará disponível em:

```txt
http://localhost:3333
```

## Rotas principais

### Status da API

```http
GET /health
```

### Informações gerais

```http
GET /api
```

### Jogadores

```http
GET /api/players
```

Também é possível filtrar jogadores usando query params:

```http
GET /api/players?club=Liverpool
GET /api/players?name=Messi
GET /api/players?nationality=Brazil
GET /api/players?position=Forward
```

Buscar jogador por ID:

```http
GET /api/players/:id
```

Criar jogador:

```http
POST /api/players
```

Atualizar estatísticas:

```http
PATCH /api/players/:id
```

Remover jogador:

```http
DELETE /api/players/:id
```

### Clubes

```http
GET /api/clubs
```

```http
GET /api/clubs/:id
```

## Exemplo de cadastro

```json
{
  "name": "Test Player",
  "club": "Real Madrid",
  "nationality": "Brazil",
  "position": "Forward",
  "statistics": {
    "Overall": 80,
    "Pace": 80,
    "Shooting": 80,
    "Passing": 80,
    "Dribbling": 80,
    "Defending": 40,
    "Physical": 75
  }
}
```

## Exemplo de atualização

```json
{
  "Pace": 90,
  "Shooting": 88
}
```

## Scripts

```json
{
  "build": "tsc --noEmit && tsup src/server.ts",
  "dist": "npm run build",
  "start:dev": "tsx --env-file=.env src/server.ts",
  "start:watch": "tsx watch --env-file=.env src/server.ts",
  "start:dist": "npm run dist && node dist/server.js"
}
```

## Estrutura

```txt
src/
  controllers/
  data/
  models/
  repositories/
  services/
  utils/
  app.ts
  routes.ts
  server.ts
```

## Aprendizados

Neste projeto foram praticados conceitos de criação de APIs REST com Express, uso de TypeScript no backend, organização em camadas, manipulação de dados em memória, leitura de JSON local, filtros por query params e tratamento de erros.

## Feito por

<a href="https://github.com/bebelle20092020j" target="_blank">
  <img src="https://img.shields.io/badge/GitHub-Isabelle%20Macedo-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub Isabelle Macedo">
</a>

