# 🔐 Django OAuth 2.0 — GitHub Login

Projeto de aprendizado que implementa autenticação OAuth 2.0 com GitHub usando Django + django-allauth.

## 📌 O que faz

- Página inicial (`/`) com botão **"Login com GitHub"**
- Autenticação via OAuth 2.0 no GitHub
- Redirecionamento para página de membros (`/members/`) após login bem-sucedido

## 🛠️ Stack

| Tecnologia | Função |
|---|---|
| Python / Django | Backend e roteamento |
| django-allauth | Provedor OAuth (GitHub) |
| GitHub OAuth App | Credenciais de autorização |

## ⚙️ Como rodar

### 1. Clone e instale as dependências

```bash
git clone https://github.com/seu-usuario/seu-repo.git
cd seu-repo
pip install -r requirements.txt
```

### 2. Configure o GitHub OAuth App

Acesse [GitHub Developer Settings](https://github.com/settings/developers) e crie um novo **OAuth App** com:

- **Homepage URL:** `http://127.0.0.1:8000`
- **Authorization callback URL:** `http://127.0.0.1:8000/accounts/github/login/callback/`

### 3. Configure as variáveis de ambiente

Crie um arquivo `.env` na raiz:

```env
GITHUB_CLIENT_ID=seu_client_id
GITHUB_CLIENT_SECRET=seu_client_secret
SECRET_KEY=sua_django_secret_key
```

### 4. Aplique as migrations e rode

```bash
python manage.py migrate
python manage.py runserver
```

Acesse `http://127.0.0.1:8000` e clique em **Login com GitHub**.

## 📚 Objetivo

Projeto didático para entender o fluxo OAuth 2.0 na prática:

1. Usuário clica em "Login com GitHub"
2. É redirecionado para a tela de autorização do GitHub
3. GitHub devolve um `code` temporário
4. django-allauth troca o `code` por um `access_token`
5. Usuário é autenticado e redirecionado para `/members/`

## 📦 Dependências principais

```
django
django-allauth
python-dotenv
```

---

> Projeto feito para aprendizado. Não use em produção sem revisar configurações de segurança.
