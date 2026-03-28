**📌📘🌐 Testes da API REST (Postman) | APP Biblioteca**

📒 Disciplina: Desenvolvimento Web Back-End
🚩 Tema: Arquitetura REST com Spring Boot e Banco de Dados H2
📦 Projeto: biblioteca-api
👨‍🏫 Professor: Abimael de Oliveira
📆 Prazo de entrega: 31/03/2026 – até 23:59
📤 Formato de entrega: Repositório GitHub + evidências visuais (screenshots)
⬆️ Nota: 0,5 (compõe nota AC1)

 

**🎯 Objetivo da atividade**
Executar testes completos da API REST da Biblioteca, validando o funcionamento real do sistema por meio de requisições HTTP via Postman.

A atividade simula um cenário profissional de backend:

👉 testar → validar → evidenciar → versionar

**🧱 Arquivos obrigatórios (desenvolvidos em sala)**
O projeto deve conter:

Livro.java
LivroRepository.java
LivroService.java
LivroController.java
data.sql
Esses arquivos representam a arquitetura em camadas aplicada na API (model, repository, service, controller), conforme trabalhado no projeto.

**🧪 CENÁRIO DE TESTES OBRIGATÓRIO (REMODELADO)**
Agora não é mais teste solto — é execução controlada de fluxo completo.

Você deverá cumprir exatamente este roteiro:

**🚀 ETAPA 1 — Validar API ativa**
Requisição:
GET /livros/teste
📌 Objetivo:
Confirmar que a API está funcionando

📸 Print obrigatório:

URL + resposta


**📚 ETAPA 2 — Consulta inicial (estado do sistema)**
Requisição:
GET /livros
📌 Objetivo:
Ver os livros já existentes no H2 (vindos do data.sql)

📸 Print obrigatório:

Lista inicial de livros


**➕ ETAPA 3 — Cadastro de 5 livros (OBRIGATÓRIO)**
Você deve cadastrar 5 livros diferentes

Requisição:
POST /livros
Exemplo de body:
{
"titulo": "Livro Teste 1",
"autor": "Aluno ADS"
}
📌 Regras:

Não repetir títulos
Fazer 5 requisições separadas
📸 Prints obrigatórios:

Pelo menos 2 requisições completas visíveis
Resultado de cada criação
IDs gerados


**🔎 ETAPA 4 — Consulta geral após cadastros**
Requisição:
GET /livros
📌 Objetivo:
Validar que os 5 livros foram realmente inseridos

📸 Print obrigatório:

Lista contendo os novos livros


**✏️ ETAPA 5 — Atualização de 2 livros (OBRIGATÓRIO)**
Escolha 2 livros cadastrados por você

Requisição:
PUT /livros/{id}
Body:
{
"titulo": "Livro Atualizado",
"autor": "Aluno ADS Atualizado",
"emprestado": false
}
📌 Objetivo:
Modificar dados do livro

📸 Prints obrigatórios:

Requisição PUT
JSON enviado
Resposta atualizada


**📚 ETAPA 6 — Fluxo de empréstimo (1 livro)**
Requisição:
PUT /livros/{id}/emprestar
📌 Objetivo:
Simular regra de negócio

📸 Print obrigatório:

Livro com emprestado = true
dataEmprestimo preenchida


**📥 ETAPA 7 — Fluxo de devolução**
Requisição:
PUT /livros/{id}/devolver
📌 Objetivo:
Validar retorno ao estado original

📸 Print obrigatório:

Livro com emprestado = false


**❌ ETAPA 8 — Remoção de 3 livros (OBRIGATÓRIO)**
Você deve excluir 3 livros

Requisição:
DELETE /livros/{id}
📌 Regras:

Usar IDs reais
Não excluir todos (deixe pelo menos 1)
📸 Prints obrigatórios:

Pelo menos 2 deletes visíveis
Status da resposta


**🔎 ETAPA 9 — Consulta final (estado pós-remoção)**
Requisição:
GET /livros
📌 Objetivo:
Validar que os livros foram removidos

📸 Print obrigatório:

Lista final atualizada


**🧪 ETAPA 10 — Validação de erro (nível profissional)**
Teste um ID inexistente:

GET /livros/9999
📌 Objetivo:
Validar tratamento de erro

📸 Print obrigatório:

Retorno de erro (404)
📸 Evidências obrigatórias (checklist)
Você deve entregar prints contendo:

✔ API funcionando (/teste)
✔ Lista inicial
✔ Cadastro dos livros
✔ Lista após cadastro
✔ Atualização
✔ Empréstimo
✔ Devolução
✔ Exclusões
✔ Lista final
✔ Teste de erro



**📂 Entrega final**
O aluno deverá:

1️⃣ Subir o projeto no GitHub
Com os arquivos trabalhados em sala

2️⃣ Atualizar o repositório com:
código funcional
commits representando evolução
3️⃣ Inserir os prints no repositório
Sugestão:

/docs/screenshots/


**✅ Critérios de avaliação**
Será avaliado:

funcionamento da API
execução correta do roteiro de testes
cumprimento das quantidades exigidas:
5 cadastros
2 atualizações
3 exclusões
coerência dos dados
clareza dos prints
organização do repositório GitHub


**⚠️ Regras importantes**
Atividade individual
Entrega fora do prazo pode ter desconto
Projeto deve estar funcional
Prints devem ser reais (não simulados)
Código sem testes evidenciados perde valor
