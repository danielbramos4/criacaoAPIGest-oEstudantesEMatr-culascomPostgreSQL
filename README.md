# 🎓 API de Gestão Escolar com FastAPI e PostgreSQL

Esta é uma API RESTful desenvolvida com **FastAPI** e **SQLAlchemy** para gerenciar o ecossistema de uma instituição de ensino. O sistema permite o cadastro e gerenciamento de estudantes, professores, disciplinas e o controle de matrículas, utilizando o **PostgreSQL** como banco de dados relacional.

---

## 🚀 Tecnologias Utilizadas

*   **Python 3**
*   **FastAPI:** Framework web moderno e de alta performance para construção de APIs.
*   **SQLAlchemy:** ORM (Object Relational Mapper) para comunicação eficiente e orientada a objetos com o banco de dados.
*   **Pydantic:** Para validação e serialização de dados (Schemas).
*   **PostgreSQL:** Sistema de gerenciamento de banco de dados relacional.
*   **Uvicorn:** Servidor ASGI para execução da aplicação.

---

## 🗄️ Estrutura do Banco de Dados

A modelagem do banco de dados reflete regras de negócio reais do ambiente acadêmico:

*   **Estudante ↔ Perfil (1:1):** Cada estudante pode ter um perfil detalhado (idade, endereço), e cada perfil pertence a um único estudante.
*   **Professor ↔ Disciplina (1:N):** Um professor pode lecionar múltiplas disciplinas, mas cada disciplina está vinculada a apenas um professor responsável.
*   **Estudante ↔ Disciplina (N:M):** Um estudante pode se matricular em várias disciplinas, e uma disciplina pode ter vários estudantes. Esse relacionamento é resolvido através da tabela associativa de **Matrículas**.

---

## 🌐 Endpoints da API

A documentação interativa (Swagger UI) é gerada automaticamente pelo FastAPI. A API disponibiliza os seguintes endpoints:

### 🧑‍🎓 Estudantes
*   `GET /estudantes/`: Lista todos os estudantes cadastrados.
*   `POST /estudantes/`: Cria um novo estudante (suporta a criação simultânea do Perfil aninhado).

### 👨‍🏫 Professores
*   `GET /professores/`: Lista todos os professores.
*   `POST /professores/`: Cadastra um novo professor.

### 📚 Disciplinas
*   `GET /disciplinas/`: Lista todas as disciplinas ofertadas.
*   `POST /disciplinas/`: Cria uma nova disciplina (exige o envio do `professor_id`).

### 📝 Matrículas
*   `GET /matriculas/`: Lista todas as matrículas ativas no sistema.
*   `POST /matriculas/`: Vincula um estudante a uma disciplina (exige o envio do `estudante_id` e `disciplina_id`).

---

## ⚙️ Como Executar o Projeto Localmente

Siga os passos abaixo para rodar a aplicação na sua máquina:

### 1. Clone o Repositório
git clone [https://github.com/danielbramos4/criacaoAPIGest-oEstudantesEMatr-culascomPostgreSQL.git](https://github.com/danielbramos4/criacaoAPIGest-oEstudantesEMatr-culascomPostgreSQL.git)

cd criacaoAPIGest-oEstudantesEMatr-culascomPostgreSQL
