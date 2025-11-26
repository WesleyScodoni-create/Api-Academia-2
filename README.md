🏋️ Academia API - Spring Boot
API RESTful completa para gerenciamento de academia desenvolvida com Spring Boot

Sistema completo de gerenciamento de academia que permite:

✅ Cadastro e gestão de alunos
✅ Gerenciamento de planos de assinatura
✅ Controle de instrutores
✅ Operações CRUD completas
✅ Validações de dados
✅ Tratamento de erros

🚀 Tecnologias Utilizadas
Java 17
Spring Boot 3.2.0
Spring Data JPA
MySQL 8.0
Maven
Lombok
Bean Validation
Spring DevTools
📁 Estrutura do Projeto
academia-api/
│
├── src/main/java/com/academia/
│   ├── AcademiaApiApplication.java        # Classe principal
│   │
│   ├── model/                              # Entidades
│   │   ├── Aluno.java
│   │   ├── Plano.java
│   │   └── Instrutor.java
│   │
│   ├── repository/                         # Repositórios JPA
│   │   ├── AlunoRepository.java
│   │   ├── PlanoRepository.java
│   │   └── InstrutorRepository.java
│   │
│   ├── service/                            # Regras de negócio
│   │   ├── AlunoService.java
│   │   ├── PlanoService.java
│   │   └── InstrutorService.java
│   │
│   └── controller/                         # Controllers REST
│       ├── AlunoController.java
│       ├── PlanoController.java
│       └── InstrutorController.java
│
├── src/main/resources/
│   └── application.properties              # Configurações
│
└── pom.xml                                 # Dependências Maven
⚙️ Pré-requisitos
Antes de começar, certifique-se de ter instalado:

Java JDK 17 ou superior
Maven 3.8+
MySQL 8.0+
Postman ou Insomnia (para testes)
Git
🔧 Instalação e Execução
1️⃣ Clone o repositório
bash
cd academia-api
2️⃣ Configure o banco de dados
Execute o script SQL para criar o banco:

sql
CREATE DATABASE academia_db;
USE academia_db;
3️⃣ Configure as credenciais
Edite o arquivo src/main/resources/application.properties:

properties
spring.datasource.url=jdbc:mysql://localhost:3306/academia_db
spring.datasource.username=root
spring.datasource.password=SUA_SENHA_AQUI
4️⃣ Compile o projeto
bash
mvn clean install
5️⃣ Execute a aplicação
bash
mvn spring-boot:run
✅ Aplicação rodando em: http://localhost:8080

🌐 Endpoints da API
📍 Base URL
http://localhost:8080/api
👤 ALUNOS (/api/alunos)
Método	Endpoint	Descrição
GET	/alunos	Lista todos os alunos
GET	/alunos/ativos	Lista apenas alunos ativos
GET	/alunos/{id}	Busca aluno por ID
POST	/alunos	Cadastra novo aluno
PUT	/alunos/{id}	Atualiza dados do aluno
DELETE	/alunos/{id}	Remove aluno
Exemplo de JSON (POST/PUT):

json
{
"nome": "João da Silva",
"cpf": "123.456.789-00",
"dataNascimento": "1995-05-10",
"telefone": "(11) 91234-5678",
"email": "joao@email.com",
"endereco": "Rua A, 123",
"peso": 75.5,
"altura": 1.75,
"ativo": true
}
💳 PLANOS (/api/planos)
Método	Endpoint	Descrição
GET	/planos	Lista todos os planos
GET	/planos/{id}	Busca plano por ID
POST	/planos	Cadastra novo plano
PUT	/planos/{id}	Atualiza plano
DELETE	/planos/{id}	Remove plano
Exemplo de JSON (POST/PUT):

json
{
"nome": "Plano Mensal Básico",
"descricao": "Acesso à musculação e área cardio",
"valorMensal": 89.90,
"duracaoMeses": 1,
"ativo": true
}
👨‍🏫 INSTRUTORES (/api/instrutores)
Método	Endpoint	Descrição
GET	/instrutores	Lista todos os instrutores
GET	/instrutores/{id}	Busca instrutor por ID
POST	/instrutores	Cadastra novo instrutor
PUT	/instrutores/{id}	Atualiza instrutor
DELETE	/instrutores/{id}	Remove instrutor
Exemplo de JSON (POST/PUT):

json
{
"nome": "Carlos Silva",
"cpf": "123.456.789-00",
"telefone": "(11) 98765-4321",
"email": "carlos@academia.com",
"especialidade": "Musculação",
"salario": 3500.00,
"dataContratacao": "2022-01-15",
"ativo": true
}
🧪 Testando com Postman
1. Listar todos os alunos
   GET http://localhost:8080/api/alunos
2. Criar novo aluno
   POST http://localhost:8080/api/alunos
   Content-Type: application/json

{
"nome": "Maria Santos",
"cpf": "222.333.444-55",
"dataNascimento": "1988-08-22",
"telefone": "(11) 92345-6789",
"email": "maria@email.com",
"endereco": "Rua B, 456",
"peso": 62.0,
"altura": 1.65,
"ativo": true
}
3. Buscar aluno específico
   GET http://localhost:8080/api/alunos/1
4. Atualizar aluno
   PUT http://localhost:8080/api/alunos/1
   Content-Type: application/json

{
"nome": "Maria Santos Silva",
"cpf": "222.333.444-55",
"dataNascimento": "1988-08-22",
"telefone": "(11) 92345-6789",
"email": "maria.santos@email.com",
"endereco": "Rua Nova, 789",
"peso": 60.0,
"altura": 1.65,
"ativo": true
}
5. Deletar aluno
   DELETE http://localhost:8080/api/alunos/1
   🔄 Versionamento
   Este projeto segue as boas práticas de versionamento solicitadas:

Estrutura de Branches:
main (branch principal)
├── semana-1 (desenvolvimento semana 1)
├── semana-2 (desenvolvimento semana 2)
├── semana-3 (desenvolvimento semana 3)
└── semana-4 (desenvolvimento semana 4)
Cronograma de Commits:
Semana	Branch	Tarefas	Commits Realizados
1	semana-1	Configuração inicial, entidades, repositories	✅ 3 commits
2	semana-2	Services e validações	✅ 2 commits
3	semana-3	Controllers e endpoints	✅ 3 commits
4	semana-4	Testes, ajustes finais, documentação	✅ 2 commits
Comandos Git Usados:
bash
# Semana 1
git checkout -b semana-1
git add .
git commit -m "feat: configuração inicial do projeto"
git commit -m "feat: criação das entidades JPA"
git commit -m "feat: implementação dos repositories"
git checkout main
git merge semana-1

# Semana 2
git checkout -b semana-2
git commit -m "feat: implementação dos services"
git commit -m "feat: adição de validações"
git checkout main
git merge semana-2

# Semana 3
git checkout -b semana-3
git commit -m "feat: criação dos controllers REST"
git commit -m "feat: implementação dos endpoints CRUD"
git commit -m "fix: tratamento de erros HTTP"
git checkout main
git merge semana-3

# Semana 4
git checkout -b semana-4
git commit -m "test: testes de endpoints com Postman"
git commit -m "docs: criação do README completo"
git checkout main
git merge semana-4
✅ Checklist de Requisitos Atendidos
CRUD completo de múltiplas entidades
Persistência com Spring Data JPA e MySQL
Camadas bem definidas (Controller, Service, Repository)
Validações com Bean Validation
Tratamento de erros adequado
README.md completo com instruções
Commits semanais (mínimo 1 por semana)
Merges semanais para a branch main
Script SQL de criação do banco
Endpoints testáveis via Postman
📊 Arquitetura do Projeto
┌─────────────┐
│  CONTROLLER │ ← Recebe requisições HTTP
└──────┬──────┘
│
↓
┌─────────────┐
│   SERVICE   │ ← Regras de negócio e validações
└──────┬──────┘
│
↓
┌─────────────┐
│ REPOSITORY  │ ← Acesso ao banco de dados
└──────┬──────┘
│
↓
┌─────────────┐
│   MYSQL DB  │ ← Persistência dos dados
└─────────────┘
🐛 Tratamento de Erros
A API retorna os seguintes códigos HTTP:

Código	Significado
200 OK	Operação bem-sucedida
201 Created	Recurso criado com sucesso
204 No Content	Exclusão bem-sucedida
400 Bad Request	Dados inválidos
404 Not Found	Recurso não encontrado
500 Internal Server Error	Erro no servidor

