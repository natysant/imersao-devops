# Imersão DevOps - Alura Google Cloud

# API de Gestão Escolar

[![Python Version](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)
[![Framework](https://img.shields.io/badge/framework-FastAPI-green.svg)](https://fastapi.tiangolo.com/)
[![Database](https://img.shields.io/badge/database-SQLite-blue.svg)](https://www.sqlite.org/index.html)

API RESTful desenvolvida com FastAPI para gerenciar alunos, cursos e matrículas em uma instituição de ensino. Este projeto foi criado como parte da Imersão DevOps da Alura.

## ✨ Funcionalidades

- **Gestão de Alunos:** CRUD completo para alunos (Criar, Ler, Atualizar, Deletar).
- **Busca de Alunos:** Pesquisa de alunos por nome (parcial) ou e-mail.
- **Gestão de Cursos:** Criação, listagem e atualização de cursos.
- **Sistema de Matrículas:**
  - Realizar matrícula de um aluno em um curso.
  - Listar todos os cursos em que um aluno está matriculado.
  - Listar todos os alunos matriculados em um determinado curso.
- **Documentação Interativa:** Geração automática de documentação da API com Swagger UI e ReDoc.

## Endpoints da API

A documentação completa e interativa está disponível em `/docs` após iniciar a aplicação.

### Alunos (`/alunos`)
- `GET /alunos`: Lista todos os alunos.
- `GET /alunos/{aluno_id}`: Busca um aluno pelo ID.
- `GET /alunos/nome/{nome_aluno}`: Busca aluno(s) por nome.
- `GET /alunos/email/{email_aluno}`: Busca um aluno pelo e-mail.
- `POST /alunos`: Cria um novo aluno.
- `PUT /alunos/{aluno_id}`: Atualiza um aluno existente.
- `DELETE /alunos/{aluno_id}`: Deleta um aluno.

### Cursos (`/cursos`)
- `GET /cursos`: Lista todos os cursos.
- `GET /cursos/{codigo_curso}`: Busca um curso pelo seu código.
- `POST /cursos`: Cria um novo curso.
- `PUT /cursos/{codigo_curso}`: Atualiza um curso existente.

### Matrículas (`/matriculas`)
- `POST /matriculas`: Cria uma nova matrícula (vincula um aluno a um curso).
- `GET /matriculas/aluno/{nome_aluno}`: Lista os cursos de um aluno.
- `GET /matriculas/curso/{codigo_curso}`: Lista os alunos de um curso.

## 🛠️ Tecnologias Utilizadas

- Python 3.10+
- FastAPI - Framework web.
- Pydantic - Para validação de dados.
- SQLAlchemy - ORM para interação com o banco de dados.
- SQLite - Banco de dados relacional.
- Uvicorn - Servidor ASGI.

## 🚀 Começando

### Pré-requisitos

- Python 3.10 ou superior
- Git
- Docker (Opcional, para containerização)

## 🗃️ Banco de Dados

- O projeto utiliza **SQLite** como banco de dados.
- O arquivo do banco, `escola.db`, será criado automaticamente na raiz do projeto na primeira vez que a aplicação for executada.
- Para reiniciar o banco de dados (apagando todos os dados), simplesmente delete o arquivo `escola.db`.

## 📁 Estrutura do Projeto
```
.
├── app.py              # Arquivo principal da aplicação FastAPI
├── database.py         # Configuração do banco de dados (SQLAlchemy)
├── models.py           # Modelos do banco de dados (tabelas)
├── schemas.py          # Schemas de validação de dados (Pydantic)
├── requirements.txt    # Lista de dependências Python
├── readme.md           # Este arquivo
└── routers/
    ├── alunos.py       # Rotas para a entidade Aluno
    ├── cursos.py       # Rotas para a entidade Curso
    └── matriculas.py   # Rotas para a entidade Matrícula
```
