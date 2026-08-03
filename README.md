<div align="center">

# 📰 Clone TabNews

**Reconstrução do [TabNews](https://www.tabnews.com.br/) acompanhando o curso [curso.dev](https://curso.dev/) — com foco em fundamentos: infraestrutura, testes e qualidade desde o primeiro commit.**

![Next.js](https://img.shields.io/badge/Next.js_15-000000?style=for-the-badge&logo=next.js&logoColor=white)
![React](https://img.shields.io/badge/React_19-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL_16-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Jest](https://img.shields.io/badge/Jest_29-C21325?style=for-the-badge&logo=jest&logoColor=white)

[**🔗 Ver o deploy**](https://clone-tabnews-hazel-ten.vercel.app)

</div>

---

## 📖 Sobre o projeto

Projeto guiado do **curso.dev**, do Filipe Deschamps. A proposta do curso é diferente da maioria: em vez de começar pela tela, começa pela base — versionamento, ambiente reproduzível, banco de dados containerizado, testes automatizados e deploy contínuo. A interface vem depois, quando o alicerce está firme.

Por isso este repositório tem `.editorconfig`, `.nvmrc`, `compose.yaml` e Jest configurados antes de existir qualquer componente. É intencional.

## ⚙️ Infraestrutura

| Arquivo | Papel |
| ------- | ----- |
| `compose.yaml` | PostgreSQL 16.14 Alpine em container |
| `.nvmrc` | Versão do Node travada (`lts/hydrogen`) — todo mundo roda a mesma |
| `.editorconfig` | Formatação consistente independente do editor |
| `package.json` | Jest configurado desde o início |

## 🚀 Como rodar localmente

### Pré-requisitos

- [Node.js](https://nodejs.org/) na versão do `.nvmrc` — com [nvm](https://github.com/nvm-sh/nvm) instalado, basta `nvm use`
- [Docker](https://www.docker.com/) e Docker Compose

### Passo a passo

```bash
git clone https://github.com/Jlvieira0909/clone-tabnews.git
cd clone-tabnews

nvm use              # usa a versão do .nvmrc
npm install

docker compose up -d # sobe o PostgreSQL
npm run dev          # servidor de desenvolvimento
```

Abra [http://localhost:3000](http://localhost:3000).

### Testes

```bash
npm test           # roda a suíte
npm run test:watch # watch mode
```

## 📁 Estrutura

```
clone-tabnews/
├── pages/
│   └── index.js        # home (Pages Router)
├── compose.yaml        # PostgreSQL
├── .nvmrc              # lts/hydrogen
├── .editorconfig
└── package.json
```

## 📊 Status

Este repositório está nos **estágios iniciais** do curso. A infraestrutura está no lugar; a aplicação, quase toda por fazer.

**Feito**
- [x] Repositório, `.gitignore` e `.editorconfig`
- [x] Node travado com `.nvmrc`
- [x] Next.js com Pages Router
- [x] PostgreSQL containerizado
- [x] Jest configurado
- [x] Deploy na Vercel

**A fazer**
- [ ] Endpoint de status (`/api/v1/status`) com verificação de conexão ao banco
- [ ] Migrações de banco
- [ ] Modelo de usuários e autenticação
- [ ] CRUD de conteúdos (posts e comentários)
- [ ] Testes de integração cobrindo os endpoints
- [ ] Interface de listagem e leitura

## 📋 Notas

- **Dependência `docker` no `package.json`** — o pacote npm chamado `docker` não é o Docker; ele está listado em `dependencies` mas não é usado (o Docker real vem do `compose.yaml`). Vale remover com `npm uninstall docker`.
- **Código de rascunho em `pages/index.js`** — há uma função `teste()` com um `console.log` não utilizada, sobra de exploração inicial.
- **Pages Router** — o curso usa a estrutura `pages/`, não o App Router. É a escolha do material, não uma limitação do Next 15.

## 🔗 Referências

- [curso.dev](https://curso.dev/) — o curso
- [TabNews](https://www.tabnews.com.br/) — o original
- [Repositório oficial do TabNews](https://github.com/filipedeschamps/tabnews.com.br)

## 🌐 Deploy

Hospedado na [Vercel](https://vercel.com/): **[clone-tabnews-hazel-ten.vercel.app](https://clone-tabnews-hazel-ten.vercel.app)**

---

<div align="center">

Feito com ❤️ por [João Luiz Vieira](https://github.com/Jlvieira0909)

</div>
