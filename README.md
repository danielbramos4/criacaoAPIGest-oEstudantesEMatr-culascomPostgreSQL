# 🎓 API de Gestão de Estudantes e Matrículas

Uma API RESTful desenvolvida com **FastAPI** e **PostgreSQL** para o gerenciamento de alunos e suas respectivas matrículas em disciplinas. Este projeto utiliza o **SQLAlchemy** como ORM para a comunicação com o banco de dados e o **Pydantic** para validação de dados.

## 🚀 Tecnologias Utilizadas

*   **Python 3**
*   **FastAPI**: Framework web rápido e moderno para construção de APIs.
*   **PostgreSQL**: Banco de dados relacional.
*   **SQLAlchemy**: ORM (Object Relational Mapper) para manipulação do banco de dados.
*   **Pydantic**: Validação de dados e serialização (Schemas).
*   **Uvicorn**: Servidor ASGI para rodar a aplicação FastAPI.
*   **Psycopg2**: Adaptador de banco de dados PostgreSQL para Python.

## ⚙️ Funcionalidades Implementadas

Até o momento, a API possui os seguintes recursos (CRUD):

*   **Estudantes:**
    *   `POST /estudantes`: Criação de um novo estudante (nome e idade).
    *   `GET /estudantes`: Listagem de todos os estudantes cadastrados.
    *   `DELETE /estudantes/{estudante_id}`: Exclusão de um estudante específico. A exclusão de um estudante aciona o *Cascade Delete*, removendo automaticamente todas as suas matrículas associadas.
*   **Matrículas:**
    *   `POST /matriculas`: Matrícula de um estudante existente em uma disciplina (vinculado pelo `estudante_id`).
    *   `GET /matriculas`: Listagem de todas as matrículas ativas.
    *   `DELETE /matriculas/{matricula_id}`: Exclusão de uma matrícula específica sem afetar o estudante.

## 📂 Estrutura do Projeto

*   `main.py`: Ponto de entrada da aplicação e definição das rotas (Endpoints).
*   `models.py`: Definição dos modelos do banco de dados usando SQLAlchemy (Tabelas `estudantes` e `matriculas`).
*   `schemas.py`: Definição dos esquemas Pydantic para validação de requisições e respostas.
*   `database.py`: Configuração da conexão com o banco de dados PostgreSQL e criação da sessão.

