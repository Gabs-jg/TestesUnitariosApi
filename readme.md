## Testes Unitários API (Spring Boot & JUnit 5)
Uma API RESTful completa desenvolvida em Java com Spring Boot, focada nas melhores práticas de arquitetura de software, tratamento de exceções customizado e uma suíte abrangente de **testes unitários** utilizando JUnit 5 e Mockito.


---
## Tecnologias Utilizadas
- **Java 21**
- **Spring Boot** (Spring Web, Spring Data JPA)
- **H2 Database** (Banco de dados em memória para ambiente local/testes)
- **JUnit 5 & Mockito** (Testes unitários e mocks)
- **ModelMapper** (Mapeamento de DTOs e Entidades)
- **Lombok** (Produtividade e redução de código boilerplate)
- **Maven** (Gerenciamento de dependências e build)
---
## Arquitetura do Projeto
O projeto segue uma arquitetura em camadas bem definida:
```text
br.com.dev.api
├── config               # Configurações do Spring (ModelMapper, Profiles)
├── domain               # Entidades de domínio (User)
│   └── dto              # Data Transfer Objects (UserDTO)
├── repositories         # Interfaces Spring Data JPA (UserRepository)
├── resources            # Controladores REST / Endpoints (UserResource)
│   └── exceptions       # Handlers de exceção global e respostas customizadas
└── services             # Interfaces e implementações das regras de negócio (UserService)
    └── exceptions       # Exceções de negócio (ObjectNotFoundException, DataIntegrityViolationException)
```
## Suíte de Testes Unitários
O objetivo principal desta aplicação é demonstrar o teste de cobertura completo das camadas da aplicação:
1. UserServiceImplTest: Valida regras de negócio, busca por ID, listagem de usuários, criação, atualização e exclusão, além de tratar exceções de violação de integridade de dados e objeto não encontrado.
2. UserResourceTest: Valida a resposta dos endpoints REST, status HTTP (200 OK, 201 Created, 204 No Content), e a conversão de/para DTOs.
3. ResourceExceptionHandlerTest: Garante que os erros e exceções capturados pela API retornem o payload padrão esperado (StandardError).
---
## Endpoints da API
| Método | Endpoint | Descrição |
| :--- | :--- | :--- |
| `GET` | `/user` | Lista todos os usuários cadastrados |
| `GET` | `/user/{id}` | Busca um usuário pelo ID |
| `POST` | `/user` | Cadastra um novo usuário |
| `PUT` | `/user/{id}` | Atualiza as informações de um usuário existente |
| `DELETE` | `/user/{id}` | Remove um usuário pelo ID |
---
## Como Executar o Projeto
**Pré-requisitos**
* **Java 21** ou superior
* **Maven** (opcional, pode usar o `./mvnw` incluso)

**Passos para execução**

1. Clone o repositório:
   ```bash
   git clone https://github.com/Gabs-jg/TestesUnitariosApi
   cd TestesUnitariosApi

Compile e execute a aplicação:

    ./mvnw spring-boot:run

No Windows, utilize mvnw.cmd spring-boot:run.

A aplicação estará disponível em http://localhost:8080.

## Como Executar os Testes Unitários

Para rodar toda a suíte de testes unitários e verificar o relatório de execução:
    ```bash

    ./mvnw clean test

