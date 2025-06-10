# 🎯 Event Manager API – Backend

Este é o backend da aplicação **Event Manager App**, um sistema para gerenciamento de campanhas de eventos em shopping centers, com foco na alocação de agentes recreadores e controle de escalas e pagamentos.

---

## 🚀 Tecnologias Utilizadas

- **NestJS** – framework Node.js para criação de APIs robustas
- **TypeORM** – ORM para abstração e mapeamento do banco de dados
- **SQLite** – banco de dados leve, ideal para MVPs e desenvolvimento local
- **JWT** – autenticação segura com tokens
- **Bcrypt** – criptografia de senhas
- **Axios (Nest HTTP)** – integração com APIs externas (ViaCEP)

---

## ⚙️ Instalação e Setup

### 1. Instale as dependências

```bash
cd backend
npm install
2. Inicie o servidor
Copiar
Editar
npm run start:dev
Por padrão, a API será executada em http://localhost:3000

🔐 Autenticação
🔑 Login
POST /auth/login

json
Copiar
Editar
{
  "username": "admin",
  "password": "admin123"
}
Retorna:

json
Copiar
Editar
{
  "access_token": "<jwt_token>",
  "user": {
    "id": 1,
    "username": "admin",
    "role": "superUser"
  }
}
👤 Dados do usuário logado
GET /auth/me
Header: Authorization: Bearer <access_token>

👥 Agentes Recreadores
POST /agents – criar agente

GET /agents – listar todos

GET /agents/:id – detalhes

PATCH /agents/:id – editar

DELETE /agents/:id – remover

🎪 Campanhas
POST /campaigns

GET /campaigns

GET /campaigns/:id

PATCH /campaigns/:id

DELETE /campaigns/:id

🗓️ Escalas
POST /scales → cria escala
✅ Gera automaticamente um pagamento com status nao-pago

GET /scales

GET /scales/:id

PATCH /scales/:id

DELETE /scales/:id

💸 Pagamentos
GET /payments

GET /payments/:id

PATCH /payments/:id

DELETE /payments/:id

⚠️ Pagamentos não são removidos automaticamente caso uma escala seja modificada ou apagada. A responsabilidade por esses ajustes é do usuário do sistema.

📬 Consulta de Endereço por CEP
GET /cep/12210010

Retorna:

json
Copiar
Editar
{
  "cep": "12210-010",
  "street": "Rua Paraibuna",
  "neighborhood": "Centro",
  "city": "São José dos Campos",
  "state": "SP",
  "complement": ""
}
🧠 Observações
Usuários são cadastrados diretamente no banco com senha criptografada (bcrypt)

Somente usuários com papel superUser podem cadastrar novos usuários

O app segue arquitetura modular e organizada com pastas por funcionalidade

🧑‍💻 Dev
Autor: João Pedro Barsaglini

Email: joaopedrobarsaglini@gmail.com

Git config:

user.name = João Pedro Barsaglini

user.email = joaopedrobarsaglini@gmail.com

📎 Repositório
🔗 https://github.com/joaopbg/event-manager-app

Feito com ❤️ usando NestJS + SQLite

yaml
Copiar
Editar

---

### ✅ Próximo passo:
Salve isso como `readme-user.md` no seu diretório backend ou raiz do repositório, e suba com:

```bash
git add readme-user.md
git commit -m "docs: adiciona readme-user.md com visão geral do backend"
git push
