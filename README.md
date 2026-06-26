# Triagem-de-Atendimentos

## Descrição

A proposta é desenvolver uma API backend simples para tiragem de atendimentos, com cadastro de usuários, criação de tickets e testes automatizados.

## Stack
- NodeJS (v26.0.0)
- TypeScript
- Express (^5.2.1)
- Prisma
- PostgreSQL
- Jest

Tudo isso subirá em um ambiente de container orquestrado por docker-compose.

## Escopo
- CRUD de user: fluxo completo de get, getById, post, put e soft-delete.
- Criação e consulta de tickets: baseado no objeto padrão ticket, que englobará a todas necessidades.
Objeto padrão (Ticket)
```
requestText: text
classifiedChannel: ENUM(channel)
status: ENUM(status)
priority: ENUM(priority)
createdAt: datetime
updatedAt: datetime
deleted: bool
```
- Classificação automatica do ticket em um canal: A ideia inicial é que será feita por type, fazendo provavelmente uma ideia de factory+strategy para lidar com o objeto levando como base seu tipo.
```
Ticket
   ↓
type = "SAC"
   ↓
Factory
   ↓
SACHandler
   ↓
process(ticket)
```
