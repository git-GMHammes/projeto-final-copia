# 🌐 Intranet Social - Sistema de Rede Social Corporativa

Sistema de intranet com funcionalidades de rede social desenvolvido para promover a comunicação, colaboração e engajamento entre colaboradores de uma organização.

## 📋 Índice

- [Sobre o Projeto](#sobre-o-projeto)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Funcionalidades](#funcionalidades)
- [Arquitetura do Sistema](#arquitetura-do-sistema)
- [Requisitos](#requisitos)
- [Instalação](#instalação)
- [Estrutura de Pastas](#estrutura-de-pastas)
- [Documentação da API](#documentação-da-api)
- [Pontos de Função](#pontos-de-função)
- [Contribuindo](#contribuindo)
- [Licença](#licença)

## 🎯 Sobre o Projeto

O **Intranet Social** é uma plataforma corporativa que integra funcionalidades de comunicação interna, compartilhamento de conhecimento e interação social entre colaboradores. O sistema visa melhorar o engajamento, facilitar a comunicação interdepartamental e criar um ambiente digital colaborativo.

### Objetivos

- Centralizar a comunicação interna da empresa
- Promover o compartilhamento de conhecimento
- Facilitar a integração entre equipes
- Aumentar o engajamento dos colaboradores
- Criar um repositório de informações corporativas

## 🚀 Tecnologias Utilizadas

### Backend

- **PHP 8.1+** - Linguagem de programação
- **CodeIgniter 4** - Framework PHP para API REST
- **JWT (JSON Web Tokens)** - Autenticação e autorização
- **Composer** - Gerenciador de dependências

### Frontend

- **ReactJS 18+** - Biblioteca JavaScript para interfaces
- **React Router DOM** - Roteamento SPA
- **Axios** - Cliente HTTP para consumo da API
- **React Hook Form** - Gerenciamento de formulários
- **Context API / Redux** - Gerenciamento de estado
- **Styled Components / TailwindCSS** - Estilização

### Banco de Dados

- **MySQL 8.0+** - Sistema de gerenciamento de banco de dados
- **InnoDB** - Engine de armazenamento

### Ferramentas de Desenvolvimento

- **Git** - Controle de versão
- **Docker** - Containerização (opcional)
- **Postman** - Testes de API
- **ESLint** - Linter JavaScript
- **PHP CS Fixer** - Padronização de código PHP

## ✨ Funcionalidades

### 👤 Gestão de Usuários

- [x] Cadastro e autenticação de usuários
- [x] Perfis de usuário personalizáveis
- [x] Upload de foto de perfil
- [x] Gerenciamento de privacidade
- [x] Níveis de acesso (Admin, Moderador, Usuário)

### 📝 Feed de Publicações

- [x] Criar, editar e excluir publicações
- [x] Curtidas e comentários
- [x] Compartilhamento de posts
- [x] Upload de imagens e arquivos
- [x] Menções a usuários (@usuario)
- [x] Hashtags (#tema)
- [x] Feed personalizado por departamento/equipe

### 💬 Mensagens

- [x] Chat privado entre usuários
- [x] Grupos de conversa
- [x] Notificações em tempo real
- [x] Histórico de conversas
- [x] Status de leitura

### 👥 Grupos e Comunidades

- [x] Criar grupos por interesse/departamento
- [x] Grupos públicos e privados
- [x] Moderação de grupos
- [x] Feed exclusivo do grupo
- [x] Membros e convites

### 📊 Área Administrativa

- [x] Dashboard com métricas
- [x] Gerenciamento de usuários
- [x] Moderação de conteúdo
- [x] Relatórios de atividade
- [x] Configurações do sistema

### 🔔 Notificações

- [x] Notificações em tempo real
- [x] Centro de notificações
- [x] Notificações por email
- [x] Preferências de notificação

### 🔍 Busca e Descoberta

- [x] Busca de usuários
- [x] Busca de publicações
- [x] Busca de grupos
- [x] Filtros avançados
- [x] Sugestões personalizadas

## 🏗️ Arquitetura do Sistema

```
┌─────────────────┐
│   ReactJS       │  Frontend - Interface do Usuário
│   (SPA)         │
└────────┬────────┘
         │ HTTP/HTTPS
         │ REST API
         ▼
┌─────────────────┐
│  CodeIgniter 4  │  Backend - Lógica de Negócio
│  (API REST)     │
└────────┬────────┘
         │ PDO/MySQLi
         ▼
┌─────────────────┐
│     MySQL       │  Banco de Dados
│   (InnoDB)      │
└─────────────────┘
```

### Padrões Utilizados

- **MVC** - Model-View-Controller (Backend)
- **Component-Based** - Arquitetura de componentes (Frontend)
- **RESTful** - Princípios REST para API
- **Repository Pattern** - Abstração de acesso a dados
- **Service Layer** - Camada de serviços de negócio

## 📦 Requisitos

### Servidor

- PHP >= 8.1
- MySQL >= 8.0
- Apache/Nginx com mod_rewrite
- Composer
- Node.js >= 16.x
- NPM ou Yarn

### Recomendado

- 2GB RAM mínimo
- 10GB espaço em disco
- SSL/TLS configurado

## 🔧 Instalação

### 1. Clone o Repositório

```bash
git clone https://github.com/sua-empresa/intranet-social.git
cd intranet-social
```

### 2. Configuração do Backend

```bash
cd backend

# Instalar dependências
composer install

# Copiar arquivo de configuração
cp env .env

# Configurar variáveis de ambiente
nano .env
```

**Configurações necessárias no .env:**

```env
# Database
database.default.hostname = localhost
database.default.database = intranet_db
database.default.username = seu_usuario
database.default.password = sua_senha
database.default.DBDriver = MySQLi

# JWT
jwt.secret = sua_chave_secreta_aqui
jwt.expire = 3600

# App
app.baseURL = http://localhost:8080
```

```bash
# Executar migrations
php spark migrate

# Executar seeders (dados iniciais)
php spark db:seed InitialSeeder

# Iniciar servidor de desenvolvimento
php spark serve
```

### 3. Configuração do Frontend

```bash
cd frontend

# Instalar dependências
npm install

# Configurar variáveis de ambiente
cp .env.example .env.local
nano .env.local
```

**Configurações necessárias no .env.local:**

```env
REACT_APP_API_URL=http://localhost:8080/api
REACT_APP_API_TIMEOUT=30000
REACT_APP_UPLOADS_URL=http://localhost:8080/uploads
```

```bash
# Iniciar servidor de desenvolvimento
npm start
```

### 4. Criação do Banco de Dados

```sql
CREATE DATABASE intranet_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

## 📁 Estrutura de Pastas

### Backend (CodeIgniter 4)

```
backend/
├── app/
│   ├── Controllers/
│   │   ├── Auth/
│   │   │   ├── LoginController.php
│   │   │   └── RegisterController.php
│   │   ├── PostController.php
│   │   ├── UserController.php
│   │   ├── CommentController.php
│   │   ├── GroupController.php
│   │   └── MessageController.php
│   ├── Models/
│   │   ├── UserModel.php
│   │   ├── PostModel.php
│   │   ├── CommentModel.php
│   │   ├── GroupModel.php
│   │   └── MessageModel.php
│   ├── Filters/
│   │   ├── JWTAuthFilter.php
│   │   └── CorsFilter.php
│   ├── Libraries/
│   │   ├── JWTHandler.php
│   │   └── FileUploader.php
│   ├── Validation/
│   │   └── CustomRules.php
│   └── Database/
│       ├── Migrations/
│       └── Seeds/
├── public/
│   ├── index.php
│   └── uploads/
└── writable/
    └── logs/
```

### Frontend (ReactJS)

```
frontend/
├── public/
│   ├── index.html
│   └── assets/
├── src/
│   ├── components/
│   │   ├── common/
│   │   │   ├── Header.jsx
│   │   │   ├── Sidebar.jsx
│   │   │   ├── Footer.jsx
│   │   │   └── Loading.jsx
│   │   ├── post/
│   │   │   ├── PostCard.jsx
│   │   │   ├── PostForm.jsx
│   │   │   ├── CommentList.jsx
│   │   │   └── LikeButton.jsx
│   │   ├── user/
│   │   │   ├── UserProfile.jsx
│   │   │   ├── UserCard.jsx
│   │   │   └── UserList.jsx
│   │   └── group/
│   │       ├── GroupCard.jsx
│   │       └── GroupMembers.jsx
│   ├── pages/
│   │   ├── Home.jsx
│   │   ├── Profile.jsx
│   │   ├── Messages.jsx
│   │   ├── Groups.jsx
│   │   ├── Login.jsx
│   │   └── Register.jsx
│   ├── contexts/
│   │   ├── AuthContext.jsx
│   │   └── NotificationContext.jsx
│   ├── services/
│   │   ├── api.js
│   │   ├── authService.js
│   │   ├── postService.js
│   │   └── userService.js
│   ├── hooks/
│   │   ├── useAuth.js
│   │   ├── usePosts.js
│   │   └── useInfiniteScroll.js
│   ├── utils/
│   │   ├── validators.js
│   │   ├── formatters.js
│   │   └── constants.js
│   ├── App.jsx
│   └── index.js
└── package.json
```

## 📡 Documentação da API

### Base URL

```
http://localhost:8080/api
```

### Autenticação

Todas as rotas protegidas requerem token JWT no header:

```
Authorization: Bearer {token}
```

### Endpoints Principais

#### Autenticação

**POST** `/auth/register`

```json
{
  "nome": "João Silva",
  "email": "joao@empresa.com",
  "senha": "senha123",
  "departamento": "TI"
}
```

**POST** `/auth/login`

```json
{
  "email": "joao@empresa.com",
  "senha": "senha123"
}
```

**Response:**

```json
{
  "success": true,
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
  "user": {
    "id": 1,
    "nome": "João Silva",
    "email": "joao@empresa.com"
  }
}
```

#### Publicações

**GET** `/posts` - Lista publicações
**GET** `/posts/:id` - Detalhes de uma publicação
**POST** `/posts` - Criar publicação

```json
{
  "conteudo": "Minha primeira publicação!",
  "privacidade": "publico",
  "imagens": ["base64..."]
}
```

**PUT** `/posts/:id` - Atualizar publicação
**DELETE** `/posts/:id` - Deletar publicação

#### Comentários

**POST** `/posts/:id/comments` - Adicionar comentário
**GET** `/posts/:id/comments` - Listar comentários
**DELETE** `/comments/:id` - Deletar comentário

#### Curtidas

**POST** `/posts/:id/like` - Curtir/descurtir
**GET** `/posts/:id/likes` - Listar curtidas

#### Usuários

**GET** `/users` - Listar usuários
**GET** `/users/:id` - Perfil do usuário
**PUT** `/users/:id` - Atualizar perfil
**POST** `/users/:id/follow` - Seguir/deixar de seguir

#### Grupos

**GET** `/groups` - Listar grupos
**POST** `/groups` - Criar grupo
**GET** `/groups/:id` - Detalhes do grupo
**POST** `/groups/:id/join` - Entrar no grupo
**GET** `/groups/:id/posts` - Posts do grupo

#### Mensagens

**GET** `/messages` - Listar conversas
**GET** `/messages/:userId` - Mensagens com usuário
**POST** `/messages` - Enviar mensagem

```json
{
  "destinatario_id": 2,
  "mensagem": "Olá!"
}
```

### Códigos de Status

- `200` - Sucesso
- `201` - Criado com sucesso
- `400` - Requisição inválida
- `401` - Não autorizado
- `403` - Acesso negado
- `404` - Não encontrado
- `422` - Erro de validação
- `500` - Erro interno do servidor

## 📊 Pontos de Função

### Análise de Pontos de Função (APF)

#### 1. Funções de Dados (ILF e EIF)

| Função de Dados    | Tipo | Complexidade | PF     |
| ------------------ | ---- | ------------ | ------ |
| Usuários           | ILF  | Média        | 10     |
| Publicações        | ILF  | Alta         | 15     |
| Comentários        | ILF  | Baixa        | 7      |
| Curtidas           | ILF  | Baixa        | 7      |
| Mensagens          | ILF  | Média        | 10     |
| Grupos             | ILF  | Média        | 10     |
| Notificações       | ILF  | Média        | 10     |
| **Subtotal Dados** |      |              | **69** |

#### 2. Funções Transacionais (EI, EO, EQ)

| Função Transacional     | Tipo | Complexidade | PF     |
| ----------------------- | ---- | ------------ | ------ |
| Login/Autenticação      | EI   | Média        | 4      |
| Registro de Usuário     | EI   | Média        | 4      |
| Criar Publicação        | EI   | Alta         | 6      |
| Editar Publicação       | EI   | Média        | 4      |
| Deletar Publicação      | EI   | Baixa        | 3      |
| Curtir/Descurtir        | EI   | Baixa        | 3      |
| Comentar                | EI   | Média        | 4      |
| Enviar Mensagem         | EI   | Média        | 4      |
| Criar Grupo             | EI   | Média        | 4      |
| Listar Publicações      | EQ   | Média        | 4      |
| Buscar Usuários         | EQ   | Média        | 4      |
| Visualizar Perfil       | EQ   | Baixa        | 3      |
| Feed Personalizado      | EO   | Alta         | 7      |
| Dashboard Admin         | EO   | Alta         | 7      |
| Relatórios              | EO   | Alta         | 7      |
| **Subtotal Transações** |      |              | **68** |

#### 3. Totais de Pontos de Função

- **Total de PF Não Ajustados:** 137
- **Fator de Ajuste (média):** 1.0
- **Total de PF Ajustados:** 137 PF

### Estimativa de Esforço

Utilizando a métrica padrão de **10 horas/PF**:

- **Total de Horas:** 137 PF × 10 h/PF = **1.370 horas**
- **Equivalente em dias úteis:** 1.370h ÷ 8h = **171 dias**
- **Equivalente em meses:** 171 dias ÷ 22 dias = **~7,8 meses**

### Distribuição do Esforço

| Fase                     | Percentual | Horas      | Dias    |
| ------------------------ | ---------- | ---------- | ------- |
| Análise e Requisitos     | 15%        | 206h       | 26      |
| Design e Arquitetura     | 10%        | 137h       | 17      |
| Desenvolvimento Backend  | 30%        | 411h       | 51      |
| Desenvolvimento Frontend | 25%        | 343h       | 43      |
| Testes e QA              | 15%        | 206h       | 26      |
| Deploy e Documentação    | 5%         | 67h        | 8       |
| **TOTAL**                | **100%**   | **1.370h** | **171** |

### Equipe Recomendada

- 1 Analista de Sistemas
- 2 Desenvolvedores Backend (PHP/CodeIgniter)
- 2 Desenvolvedores Frontend (React)
- 1 DBA
- 1 QA/Tester
- 1 DevOps (parcial)

**Prazo estimado com equipe completa:** 4-5 meses

## 🗄️ Modelo de Dados (Principais Tabelas)

```sql
-- Usuários
CREATE TABLE usuarios (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    senha VARCHAR(255) NOT NULL,
    foto_perfil VARCHAR(255),
    bio TEXT,
    departamento VARCHAR(50),
    cargo VARCHAR(50),
    nivel_acesso ENUM('admin', 'moderador', 'usuario') DEFAULT 'usuario',
    ativo BOOLEAN DEFAULT TRUE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);

-- Publicações
CREATE TABLE publicacoes (
    id INT PRIMARY KEY AUTO_INCREMENT,
    usuario_id INT NOT NULL,
    conteudo TEXT NOT NULL,
    privacidade ENUM('publico', 'privado', 'grupo') DEFAULT 'publico',
    grupo_id INT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP,
    FOREIGN KEY (usuario_id) REFERENCES usuarios(id) ON DELETE CASCADE,
    FOREIGN KEY (grupo_id) REFERENCES grupos(id) ON DELETE CASCADE
);

-- Comentários
CREATE TABLE comentarios (
    id INT PRIMARY KEY AUTO_INCREMENT,
    publicacao_id INT NOT NULL,
    usuario_id INT NOT NULL,
    comentario TEXT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (publicacao_id) REFERENCES publicacoes(id) ON DELETE CASCADE,
    FOREIGN KEY (usuario_id) REFERENCES usuarios(id) ON DELETE CASCADE
);

-- Curtidas
CREATE TABLE curtidas (
    id INT PRIMARY KEY AUTO_INCREMENT,
    publicacao_id INT NOT NULL,
    usuario_id INT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    UNIQUE KEY unique_like (publicacao_id, usuario_id),
    FOREIGN KEY (publicacao_id) REFERENCES publicacoes(id) ON DELETE CASCADE,
    FOREIGN KEY (usuario_id) REFERENCES usuarios(id) ON DELETE CASCADE
);

-- Grupos
CREATE TABLE grupos (
    id INT PRIMARY KEY AUTO_INCREMENT,
    nome VARCHAR(100) NOT NULL,
    descricao TEXT,
    tipo ENUM('publico', 'privado') DEFAULT 'publico',
    criador_id INT NOT NULL,
    foto_capa VARCHAR(255),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (criador_id) REFERENCES usuarios(id) ON DELETE CASCADE
);

-- Mensagens
CREATE TABLE mensagens (
    id INT PRIMARY KEY AUTO_INCREMENT,
    remetente_id INT NOT NULL,
    destinatario_id INT NOT NULL,
    mensagem TEXT NOT NULL,
    lida BOOLEAN DEFAULT FALSE,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (remetente_id) REFERENCES usuarios(id) ON DELETE CASCADE,
    FOREIGN KEY (destinatario_id) REFERENCES usuarios(id) ON DELETE CASCADE
);
```

## 🧪 Testes

### Backend (PHPUnit)

```bash
cd backend
./vendor/bin/phpunit
```

### Frontend (Jest)

```bash
cd frontend
npm test
```

### Coverage

```bash
# Backend
composer test:coverage

# Frontend
npm run test:coverage
```

## 🚀 Deploy

### Produção

1. **Build do Frontend**

```bash
cd frontend
npm run build
```

2. **Configurar servidor web (Apache/Nginx)**
3. **Configurar SSL/TLS**
4. **Ajustar permissões de pastas**

```bash
chmod -R 755 backend/writable
chmod -R 755 backend/public/uploads
```

5. **Otimizar autoloader**

```bash
composer install --optimize-autoloader --no-dev
```

### Docker (Opcional)

```bash
docker-compose up -d
```

## 🤝 Contribuindo

1. Fork o projeto
2. Crie uma branch para sua feature (`git checkout -b feature/MinhaFeature`)
3. Commit suas mudanças (`git commit -m 'Adiciona nova feature'`)
4. Push para a branch (`git push origin feature/MinhaFeature`)
5. Abra um Pull Request

### Padrões de Código

- **PHP:** PSR-12
- **JavaScript:** ESLint + Airbnb Style Guide
- **Commits:** Conventional Commits

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## 👥 Equipe

- **Product Owner:** [Nome]
- **Scrum Master:** [Nome]
- **Tech Lead:** [Nome]
- **Desenvolvedores:** [Nomes]

## 📞 Contato

- **Email:** suporte@empresa.com
- **Slack:** #intranet-social
- **Issues:** [GitHub Issues](https://github.com/sua-empresa/intranet-social/issues)

## 📚 Documentação Adicional

- [Guia de Contribuição](CONTRIBUTING.md)
- [Código de Conduta](CODE_OF_CONDUCT.md)
- [Changelog](CHANGELOG.md)
- [Roadmap](ROADMAP.md)

---

**Desenvolvido com ❤️ pela equipe de TI**

_Última atualização: Janeiro 2026_
