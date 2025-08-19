# Explorando Padrões de Projeto na Prática com Java

Este repositório contém a implementação de diversos padrões de projeto explorados no Lab **"Explorando Padrões de Projeto na Prática com Java"**, utilizando o **Spring Framework** como base para construção de uma API REST robusta e extensível.

## 🧠 Padrões de Projeto Aplicados

Este projeto demonstra o uso prático de alguns dos principais padrões do catálogo GoF:

- **Singleton**  
  Classes anotadas com `@Service` e `@Repository` são gerenciadas pelo Spring como instâncias únicas, garantindo consistência e economia de recursos.

- **Strategy**  
  A interface `ClienteService` define uma estratégia de negócio que pode ser facilmente substituída por outras implementações, promovendo flexibilidade e desacoplamento.

- **Facade**  
  O `ClienteRestController` atua como uma fachada, simplificando o acesso à lógica de negócio e às integrações externas (como a API ViaCEP e o banco H2).

- **Repository**  
  O `ClienteRepository` abstrai o acesso ao banco de dados, permitindo consultas dinâmicas como `findByNomeContainingIgnoreCase` sem necessidade de SQL explícito.

## Funcionalidade Adicional: Busca por Nome

Foi adicionado um novo endpoint para facilitar a busca de clientes por nome, ignorando maiúsculas/minúsculas:

GET /clientes/buscar?nome=ana

Código

### Exemplo de resposta:

```json
[
  {
    "id": 1,
    "nome": "Ana Paula",
    "endereco": {
      "cep": "29090-100",
      "logradouro": "Rua das Flores",
      "cidade": "Vitória",
      "estado": "ES"
    }
  }
]

## Tecnologias Utilizadas

-Java 17

- Spring Boot

- Spring Data JPA

- H2 Database

- OpenAPI (Swagger)

- Maven

## Como Executar o Projeto

Pré-requisitos:

JDK 17 instalado

Maven configurado

IDE (VS Code, IntelliJ, etc.)

Clonar o repositório:

bash
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio
Executar a aplicação:

bash
mvn spring-boot:run
Acessar a API:

Base URL: http://localhost:8080/clientes

Teste os endpoints com Postman, Insomnia ou navegador

## Observações
O projeto utiliza banco de dados H2 em memória, reiniciado a cada execução.

A integração com a API ViaCEP permite preenchimento automático de endereço a partir do CEP informado.

## Executando o Projeto no Terminal
Para Windows (CMD ou PowerShell)
Certifique-se de estar na pasta raiz do projeto (onde está o arquivo mvnw.cmd):

*cmd*

mvnw spring-boot:run

Ou, se estiver usando PowerShell:

*powershell*

.\mvnw spring-boot:run

*Para Linux ou macOS*

Abra o terminal e navegue até a pasta do projeto:

*bash*

./mvnw spring-boot:run

- Se preferir usar o Maven instalado no sistema (em qualquer SO), use:

bash

mvn spring-boot:run

Testando a API


Depois de rodar o projeto, acesse:

Swagger UI: http://localhost:8080/swagger-ui.html

Banco H2: http://localhost:8080/h2-console

JDBC URL: jdbc:h2:mem:testdb

Usuário: sa

Senha: (deixe em branco)