# 🏨 Stay Vanilla — Core Engine

<br />

> ⚡ **Nota de Arquitetura: Do Vanilla ao Moderno**
>
> - **Este Repositório:** Abordagem purista feita 100% no braço com a _Vanilla Tech Stack_ (Zero Frameworks)..
>   <br />
>   <br />
> - **Versão Moderna:** React, Fastify, TS, Prisma, Postgres...
>   - Acesse em: **[Stay Vanilla - Modern Version](https://github.com/Dev-HideyukiTakahashi/stay-vanilla-modern)**

---

## 📌 Sobre o Projeto

O **Stay Vanilla** é um ecossistema de gestão e reservas para um hotel boutique de luxo. Concebido como um manifesto técnico, o projeto possui **zero dependências externas**. Todo o roteamento, ciclo de vida de requisições, persistência, segurança e renderização híbrida foram construídos do zero usando módulos nativos do Node.js e manipulação cirúrgica de DOM.

---

## 🔗 Links Úteis e Documentação Completa

- 📝 **Documentação (PRD, Requisitos & Regras de Negócio):** [Acesse o Projeto no Notion](https://app.notion.com/p/StayVanilla-Sistema-de-Reservas-de-Hotel-3043a302750380d8abd8d02dc3fff408?source=copy_link)
- 🎨 **Design System & Protótipo :** [Acesse o Layout no Figma](https://www.figma.com/design/Cu6MJr49WRyYNSFK5LBram/stay-vanilla?node-id=0-1&t=yxpa03HHgnNWHn2a-1)

---

## 🛠️ Stack Tecnológica (Vanilla & Core)

- **Backend:** Node.js (`http`, `fs/promises`, `crypto`, `path`, `stream`).
- **Banco de Dados:** SQLite (Driver nativo `sqlite3` com queries SQL cruas).
- **Frontend:** HTML5, CSS3 estrutural e Vanilla JavaScript (ES6+).
- **Renderização:** Server-Side Rendering (SSR) parcial dinâmico por substituição nativa de strings.

---

## 🚀 Destaques de Engenharia & Arquitetura

- **Custom Router:** Parsing de corpo (Streams), query strings e parâmetros dinâmicos (`/api/rooms/:id`) sem Express.
- **Arquitetura Clean & SOLID:** Separação estrita entre _Controllers_, _Services_ isolados e persistência via _Repositories_.
- **Garantia ACID:** Controle de concorrência direto via transações SQL cruas para anular cenários de _Overbooking_.
- **Segurança Nativa:** Gerenciamento de sessões com senhas criptografadas via `node:crypto` e cookies com flags `HttpOnly` e `SameSite=Strict`.
- **Performance Híbrida:** Uso do modo `WAL (Write-Ahead Logging)` no SQLite e renderização reativa via **Manual DOM Diffing** e **Event Delegation** no cliente.

---

## 💼 Regras de Negócio Implementadas (Resumo)

1. **Regimes Específicos & Concierge:** Alinhamento automático de consumos e comodidades extras acoplados à reserva ativa.
2. **Janelas de Horário Estritas:** Check-in às 14h e Check-out até as 11h, com gatilho automático de diária extra por atraso.
3. **Rotinas Automatizadas (Cron):** Cancelamento automático por _No-Show_ às 20h00 com liberação imediata do inventário.

---

## 🔧 Como Executar o Projeto

### Pré-requisitos

- Node.js instalado (Versão utilizada: **v24.16.0**)

### Passo a Passo

```bash
# 1. Clone o repositório
git clone https://github.com/Dev-HideyukiTakahashi/stay-vanilla-core.git

cd stay-vanilla-core

# 2. Inicialize o banco de dados e as tabelas nativas
npm run db:setup

# 3. Inicie o servidor de desenvolvimento
npm run dev

# 4. Acesse no navegador:
http://localhost:3000
```

💡Nota: O arquivo `.env` foi mantido no repositório apenas para facilitar a inicialização e apresentação. Em produção, ele seria ignorado via .gitignore.

---

✉️ Contato & Portfólio

LinkedIn: [Hideyuki Takahashi](https://www.linkedin.com/in/dev-hideyukitakahashi/)

E-mail: dev.hideyukitakahashi@gmail.com

---
