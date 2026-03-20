# Biblioteca API Aula05 - Spring Boot (Back-End)

🎯 Objetivo da atividade
Desenvolver uma API REST de Biblioteca Universitária utilizando Spring Boot, aplicando arquitetura em camadas e integração com banco de dados em memória (H2).

O projeto simula o fluxo real de uma aplicação back-end moderna:

Cliente → API → Banco de Dados → Resposta

Ao final da atividade, o(a) estudante deverá ser capaz de:

✔ criar e executar uma API Spring Boot no VS Code
✔ organizar o projeto em arquitetura em camadas (controller, service, repository, model)
✔ implementar operações CRUD
✔ simular regras de negócio (empréstimo e devolução)
✔ testar endpoints com ferramentas HTTP (Postman, Insomnia ou Thunder Client)
✔ documentar a execução com evidências visuais padronizadas

🧱 Escopo funcional obrigatório
A API deverá permitir as seguintes operações:

📘 Listar livros
🔎 Buscar livro por ID
➕ Cadastrar livro
✏ Atualizar livro
❌ Remover livro
📚 Simular empréstimo de livro
📥 Simular devolução de livro
🧪 Expor endpoint de teste para validar que a API está ativa

⚙️ Requisitos técnicos obrigatórios
O projeto deverá utilizar:

Java 17

Spring Boot

Maven (preferencialmente com Maven Wrapper)

Spring Web

Spring Data JPA

H2 Database

Lombok (opcional, porém recomendado)

Arquitetura em camadas

Estrutura mínima esperada do projeto:

biblioteca-api
│
├── controller
│   └── LivroController.java
│
├── service
│   └── LivroService.java
│
├── repository
│   └── LivroRepository.java
│
├── model
│   └── Livro.java
│
└── BibliotecaApiApplication.java
🚀 Guia de desenvolvimento (passo a passo)
Etapa 1 — Preparação do ambiente
Verifique a instalação do Java:

java -version
Versão esperada: Java 17

Instalar:

Visual Studio Code

Extension Pack for Java

Spring Boot Extension Pack

Etapa 2 — Criação do projeto
No VS Code:

1️⃣ Abrir a paleta de comandos

Ctrl + Shift + P
2️⃣ Executar:

Spring Initializr: Create a Maven Project
Configurações do projeto:

Language: Java
Group: com.facens
Artifact: biblioteca-api
Packaging: Jar
Java: 17

Dependências:

Spring Web

Spring Data JPA

H2 Database

Lombok

Spring Boot DevTools

Etapa 3 — Configuração do banco H2
No arquivo application.properties, configurar o banco em memória.

Resultado esperado:

✔ API executando com banco em memória
✔ Console do banco disponível em:

http://localhost:8080/h2-console
Etapa 4 — Modelagem da entidade
Criar a classe Livro contendo, no mínimo:

id

titulo

autor

emprestado

dataEmprestimo (ou campo equivalente)

Etapa 5 — Repositório
Criar a interface:

LivroRepository
Estendendo:

JpaRepository<Livro, Long>
Etapa 6 — Camada de serviço
Implementar LivroService contendo regras de negócio para:

CRUD completo

empréstimo de livro (não permitir emprestar livro já emprestado)

devolução de livro (não permitir devolver livro não emprestado)

Etapa 7 — Controller e endpoints
Criar LivroController com mapeamento base:

/livros
Endpoints obrigatórios:

GET    /livros
GET    /livros/teste
GET    /livros/{id}

POST   /livros

PUT    /livros/{id}

DELETE /livros/{id}

PUT    /livros/{id}/emprestar
PUT    /livros/{id}/devolver
Etapa 8 — Dados iniciais (recomendado)
Criar arquivo:

data.sql
Para inserir livros de exemplo automaticamente na inicialização da aplicação.

Etapa 9 — Execução da aplicação
Executar o projeto utilizando Maven Wrapper.

No terminal:

Windows:

.\mvnw.cmd spring-boot:run
Linux / macOS:

./mvnw spring-boot:run
Aplicação disponível em:

http://localhost:8080
Etapa 10 — Testes de cenário (obrigatórios)
Executar e evidenciar os seguintes fluxos:

📘 Consulta de catálogo

GET /livros
➕ Cadastro de livro

POST /livros
🔎 Consulta por ID

GET /livros/{id}
✏ Atualização

PUT /livros/{id}
📚 Empréstimo

PUT /livros/{id}/emprestar
📥 Devolução

PUT /livros/{id}/devolver
❌ Remoção

DELETE /livros/{id}
