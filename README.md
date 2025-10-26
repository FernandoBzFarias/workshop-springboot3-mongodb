# 🚀 API Blog - Workshop Spring Boot 3 e MongoDB

<p align="center">
  <a href="https://github.com/SEU_USUARIO/SEU_REPOSITORIO/actions">
    <img alt="Status" src="https://img.shields.io/badge/Status-Concluído-brightgreen.svg" />
  </a>
  <a href="https://www.java.com/">
    <img alt="Linguagem" src="https://img.shields.io/badge/Java-21-red.svg" />
  </a>
  <a href="https://spring.io/projects/spring-boot">
    <img alt="Framework" src="https://img.shields.io/badge/Spring_Boot-3.x-green.svg" />
  </a>
  <a href="https://docs.mongodb.com/">
    <img alt="Banco de Dados" src="https://img.shields.io/badge/MongoDB-NoSQL-4EA94B.svg" />
  </a>
  <a href="https://maven.apache.org/">
    <img alt="Build" src="https://img.shields.io/badge/Build-Maven-C71A36.svg" />
  </a>
</p>

---

## 📜 Sobre o Projeto

Este projeto é uma **API RESTful completa** desenvolvida como parte de um workshop focado no ecossistema Spring Boot, utilizando as funcionalidades mais recentes do **Spring Boot 3**.

O objetivo principal é simular as operações essenciais de um sistema de blog/rede social, com foco na **gestão de usuários** e **posts**, utilizando o **MongoDB** como banco de dados NoSQL.

### Funcionalidades Principais

- **Usuários (Users):** Cadastro, consulta (por ID e lista), atualização e exclusão.
- **Posts:** Cadastro de posts com autor referenciado e comentários aninhados.
- **Buscas Personalizadas:** Endpoint para buscar posts pelo título (`/titlesearch`).
- **Relacionamentos:** Consulta de todos os posts de um usuário específico.

### Arquitetura

A aplicação segue o padrão arquitetural em **camadas**, garantindo a separação de responsabilidades, manutenibilidade e escalabilidade:

- **Resource/Controller:** Responsável por receber as requisições HTTP e retornar as respostas.
- **Service:** Contém as regras de negócio e realiza a comunicação com o repositório.
- **Repository (Spring Data MongoDB):** Responsável pela interação com o banco de dados.
- **DTOs:** Utilizados para a transferência segura e eficiente de dados entre as camadas.
- **Global Exception Handler:** Para tratamento padronizado de erros (ex: `404 Not Found`).

---

## 🛠️ Tecnologias Utilizadas

| Categoria | Tecnologia | Detalhes |
| :--- | :--- | :--- |
| **Linguagem** | **Java** | Versão 21 |
| **Framework** | **Spring Boot** | Versão 3.x |
| **Persistência** | **Spring Data MongoDB** | Conexão e manipulação do banco NoSQL |
| **Banco de Dados** | **MongoDB** | Banco de dados NoSQL focado em documentos |
| **Build** | **Apache Maven** | Gerenciador de dependências e build |
| **IDE** | **Spring Tool Suite (STS) / Eclipse** | Ambiente de desenvolvimento |
| **Testes de API** | **Postman** | Para testar e validar os endpoints da API |

---

## ⚙️ Configuração e Execução

### Pré-requisitos

Antes de executar o projeto, você precisa ter instalado:

1.  **Java 21** ou superior
2.  **Maven**
3.  **MongoDB** (Localmente ou acesso a uma instância na nuvem)

### Passos

1.  **Clone o Repositório:**
    ```bash
    git clone [https://github.com/SEU_USUARIO/SEU_REPOSITORIO.git](https://github.com/SEU_USUARIO/SEU_REPOSITORIO.git)
    cd SEU_REPOSITORIO
    ```

2.  **Configurar o MongoDB:**
    Edite o arquivo `src/main/resources/application.properties` (ou `application.yml`) e configure o URI de conexão:

    ```properties
    # Exemplo para MongoDB local na porta padrão
    spring.data.mongodb.uri=mongodb://localhost:27017/workshop-mongo
    ```

3.  **Executar a Aplicação:**
    O projeto pode ser executado diretamente pela IDE (Eclipse/STS) ou via linha de comando:

    ```bash
    # Compila e executa o Spring Boot
    ./mvnw spring-boot:run 
    ```
    A aplicação será iniciada na porta padrão `8080`.

> **Nota:** A classe `Instantiation.java` popula o banco de dados com usuários e posts de teste ao iniciar a aplicação (limpando coleções existentes).

---

## 🌐 Endpoints da API (Com Postman)

A API expõe os seguintes endpoints, acessíveis na URL base `http://localhost:8080`.

### 1. Usuários (`/users`)

| Método | Endpoint | Descrição | Corpo da Requisição (JSON) |
| :--- | :--- | :--- | :--- |
| `GET` | `/users` | Lista todos os usuários. | N/A |
| `GET` | `/users/{id}` | Busca um usuário pelo ID. | N/A |
| `POST` | `/users` | Insere um novo usuário. | `{ "name": "...", "email": "..." }` |
| `PUT` | `/users/{id}` | Atualiza nome e email do usuário. | `{ "name": "...", "email": "..." }` |
| `DELETE` | `/users/{id}` | Exclui um usuário pelo ID. | N/A |
| `GET` | `/users/{id}/posts` | **Busca todos os posts de um usuário.** | N/A |

### 2. Posts (`/posts`)

| Método | Endpoint | Descrição | Corpo da Requisição (JSON) |
| :--- | :--- | :--- | :--- |
| `GET` | `/posts/{id}` | Busca um post pelo ID. | N/A |
| `GET` | `/posts/titlesearch?text={termo}` | **Busca posts que contenham o termo no título.** | N/A |

> **Exemplo de Busca:** `GET /posts/titlesearch?text=viagem`

---

## 👤 Autor

Desenvolvido por **[Fernando Riverson]**.


- **LinkedIn:** [Linkedin](https://www.linkedin.com/in/fernandobsfrias/)
