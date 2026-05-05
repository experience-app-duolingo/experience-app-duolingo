# 🎮 Plataforma de Aprendizado Gamificado

> Aprenda Expo e AWS de forma progressiva, interativa e gamificada — inspirado no Duolingo.

---

## 🎯 Visão Geral

Uma plataforma mobile-first que transforma o aprendizado de tecnologia em uma experiência engajante, com microliçõess, exercícios interativos, progressão por níveis e recompensas. O foco inicial são dois cursos:

- **Expo (React Native)** — do zero ao deploy
- **AWS Nuvem** — conceitos de cloud até serviços essenciais

---

## 🚩 Problema

| Desafio | Impacto |
|---|---|
| Alta evasão em cursos online | Alunos não concluem |
| Dificuldade de manter constância | Aprendizado fragmentado |
| Excesso de teoria | Pouca absorção prática |
| Falta de feedback imediato | Desmotivação |

---

## 👥 Público-Alvo

- Estudantes de ADS / Engenharia
- Iniciantes em desenvolvimento mobile
- Iniciantes em cloud computing

---

## 📚 Cursos

<details>
<summary><strong>Curso 1 — Expo (React Native)</strong></summary>

- Fundamentos
- Componentes
- Navegação
- APIs
- Armazenamento
- Build e Deploy

</details>

<details>
<summary><strong>Curso 2 — AWS Nuvem</strong></summary>

- Conceitos de Cloud
- IAM
- S3
- EC2
- Lambda
- API Gateway
- DynamoDB

</details>

---

## ✨ Funcionalidades

### 🔐 Autenticação
Cadastro, login, recuperação de senha e edição de perfil.

### 🗺️ Trilhas de Aprendizado
Cursos → Módulos → Lições com progressão linear e bloqueio por pré-requisito.

### 📖 Lição
Cada lição contém explicação curta + exercícios interativos + feedback imediato.

**Tipos de exercícios:**
- Múltipla escolha
- Verdadeiro/Falso
- Associação
- Completar código
- Ordenar passos

### 🏆 Gamificação
| Elemento | Descrição |
|---|---|
| XP | Pontos ganhos por lição concluída |
| Níveis | Progressão baseada em XP acumulado |
| Streak | Ofensiva diária de atividade |
| Conquistas | Badges por marcos atingidos |
| Ranking | Opcional (Fase 2) |

### 📊 Progresso
Acompanhamento por curso, módulo e lição, com histórico e taxa de acerto.

### 🧠 Revisão Inteligente *(Fase 2)*
Identifica erros recorrentes, sugere revisão e gera exercícios adaptativos.

### ⚙️ Administração
CRUD completo de cursos, módulos, lições e exercícios + relatórios de uso.

---

## 🗺️ Jornada do Usuário

```
Criar conta → Escolher curso → Iniciar lição → Realizar exercícios
     → Receber feedback → Ganhar XP → Avançar na trilha
          → Manter streak → Receber sugestões de revisão
```

---

## 📐 Arquitetura

```
┌─────────────────────────────────────────────────┐
│                   Frontend                       │
│   Expo (mobile)        React/Next.js (admin)     │
└────────────────────────┬────────────────────────┘
                         │
┌────────────────────────▼────────────────────────┐
│                   Backend                        │
│           Node.js / Java / Python                │
└────────────────────────┬────────────────────────┘
                         │
┌────────────────────────▼────────────────────────┐
│              AWS Infrastructure                  │
│  API Gateway → Lambda → DynamoDB                 │
│  S3 (assets)     Cognito / JWT (auth)            │
└─────────────────────────────────────────────────┘
```

---

## 🗄️ Modelo de Dados

```
Usuario          Curso            Modulo
─────────        ──────           ───────
id               id               id
nome             nome             cursoId
email            descricao        ordem
xp
nivel            Licao            Exercicio
streak           ─────            ─────────
                 id               id
                 moduloId         licaoId
                 ordem            tipo
                                  pergunta
Progresso                         respostas
─────────                         respostaCorreta
userId
cursoId
moduloAtual
licaoAtual
xpAcumulado
```

---

## 🚀 Roadmap

| Fase | Foco | Status |
|---|---|---|
| **Fase 1 — MVP** | Trilha básica, exercícios simples, XP, streak, painel básico | 🔨 Em desenvolvimento |
| **Fase 2** | Gamificação completa, revisão inteligente, dashboard avançado | 📋 Planejado |
| **Fase 3** | Novos cursos, IA adaptativa, multiplayer / ranking | 🔮 Futuro |

### ✅ MVP inclui
- Cadastro e login
- 2 cursos (Expo + AWS)
- Trilha simples com progressão
- Exercícios de múltipla escolha
- XP, progresso e streak simples
- Painel básico

### ❌ Fora do MVP
- Ranking
- IA adaptativa avançada
- Notificações push avançadas

---

## 📏 Regras de Negócio

- Usuário pode cursar Expo e AWS simultaneamente
- Progresso é independente por curso
- Lição só é concluída com mínimo de acerto
- Conteúdo é desbloqueado progressivamente
- Streak exige atividade diária
- Revisão é baseada nos erros do próprio usuário

---

## 📈 KPIs

- Taxa de retenção (D1, D7, D30)
- Número médio de lições por usuário
- Taxa de conclusão de módulos
- Tempo médio de uso diário
- Taxa de acerto por exercício
- Manutenção de streak

---

## ⚠️ Riscos

- Baixa retenção inicial
- Conteúdo insuficiente nas primeiras versões
- Dificuldade de balancear a gamificação
- Complexidade crescente no backend
- Necessidade constante de atualização de conteúdo

---

## 🛠️ Stack

| Camada | Tecnologia |
|---|---|
| Mobile | Expo / React Native |
| Admin | React / Next.js |
| Backend | Node.js / Java / Python |
| Banco de dados | DynamoDB |
| Storage | S3 |
| Funções | Lambda |
| API | API Gateway |
| Auth | JWT ou Cognito |
| Cloud | AWS |
