# Conta Service 2025

Este projeto foi desenvolvido como parte de um estudo sobre back-end em Java no **Instituto Matera**. Ele implementa um serviço de gerenciamento de contas bancárias utilizando o framework **Spring Boot**.

## Resumo do Projeto

O **Conta Service** é uma aplicação que permite criar, buscar, atualizar e deletar contas bancárias. Além disso, o serviço integra-se a um simulação de **Sistema do Bacen** para gerenciar chaves Pix associadas às contas. A aplicação utiliza um banco de dados H2 para persistência e segue boas práticas de desenvolvimento, como o uso de DTOs, validação de dados e tratamento de exceções.

## Dependências Principais

- **Spring Boot Starter Web**: Para criação de APIs REST.
- **Spring Boot Starter Data JPA**: Para integração com o banco de dados.
- **Spring Boot Starter Validation**: Para validação de dados de entrada.
- **Spring Cloud OpenFeign**: Para comunicação com serviços externos (Bacen).
- **H2 Database**: Banco de dados em memória para desenvolvimento e testes.
- **Lombok**: Para reduzir o boilerplate de código.
- **Springdoc OpenAPI**: Para documentação da API.

## Estrutura de Classes de Serviço

### `ContaService`
- **Descrição**: Contém a lógica de negócios para o gerenciamento de contas bancárias.
- **Principais Métodos**:
    - `criarConta`: Cria uma nova conta e registra a chave Pix no Bacen.
    - `buscaTodasContas`: Retorna todas as contas cadastradas.
    - `buscaContaById`: Busca uma conta específica pelo ID.
    - `atualizarConta`: Atualiza os dados de uma conta existente.
    - `deletarConta`: Remove uma conta pelo ID.

### `PixService`
- **Descrição**: Gerencia operações relacionadas às chaves Pix.
- **Uso**: Integra-se ao Bacen para criar e validar chaves Pix.

### Integração com o "Sistema BACEN"
A integração com o Bacen é realizada através do cliente Feign (`BacenService`), que permite registrar e consultar chaves Pix de forma simplificada.

## Como Executar

1. Certifique-se de ter o **Java 17+** instalado.
2. Clone o repositório e navegue até o diretório do projeto.
3. Execute o comando abaixo para iniciar a aplicação:
     ```bash
     ./mvnw spring-boot:run
     ```
4. Acesse a aplicação em `http://localhost:9000`.

## Documentação da API

A documentação da API está disponível em:
```
http://localhost:9000/swagger-ui.html
```

## Conclusão

Este projeto é uma excelente introdução ao desenvolvimento de APIs RESTful em Java, utilizando o ecossistema Spring. Ele demonstra conceitos importantes como persistência de dados, integração com serviços externos e boas práticas de design de software.  
