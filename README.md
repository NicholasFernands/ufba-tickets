# UFBA Tickets — Backend

Backend de uma aplicação acadêmica voltada ao **gerenciamento e exploração de eventos**, com recursos para usuários, eventos, atrações, locais e avaliações.

## Objetivo

Desenvolver uma API REST utilizando Java e Spring Boot para organizar informações de eventos e seus relacionamentos em um banco de dados relacional.

## O que o projeto faz

A API permite:

- Cadastrar e gerenciar usuários.
- Criar, consultar, atualizar e excluir eventos.
- Filtrar eventos por nome e categoria.
- Gerenciar atrações associadas a eventos.
- Gerenciar locais.
- Criar e consultar avaliações.
- Realizar login de usuários.

## Tecnologias

- **Java 17**
- **Spring Boot**
- **Spring Web**
- **Spring Data JPA**
- **Hibernate**
- **MySQL**
- **Bean Validation**
- **Lombok**
- **Gradle Kotlin DSL**
- **JUnit / Spring Boot Test**

## Arquitetura

A aplicação é organizada por domínio:

```text
src/main/java/com/ufbatickets/project/
├── eventos/
├── atracoes/
├── avaliacoes/
├── locais/
├── usuários/
├── config/
└── utils/
```

O fluxo de persistência segue a estrutura:

```text
Cliente
  │
  ▼
Controller
  │
  ▼
Repository
  │
  ▼
JPA / Hibernate
  │
  ▼
MySQL
```

## Modelagem

```text
Usuario
 ├── 1:N ──> Evento
 ├── 1:N ──> Local
 └── 1:N ──> Avaliacao

Evento
 ├── 1:N ──> Atracao
 └── 1:N ──> Avaliacao
```

O modelo representa os principais elementos de uma plataforma de eventos e seus relacionamentos.

## Como clonar

```bash
git clone https://github.com/NickFernands/ufba-tickets.git
cd ufba-tickets
```

## Como executar

Pré-requisitos: **JDK 17**, **MySQL** e o **Gradle Wrapper**.

Configure o banco em `src/main/resources/application.properties` e execute:

Linux/macOS:

```bash
./gradlew bootRun
```

Windows:

```powershell
.\gradlew.bat bootRun
```

### Testes

```bash
./gradlew test
```

## Observação

Apesar do nome `UFBA Tickets`, o código analisado está focado no gerenciamento de eventos e entidades relacionadas. Não há implementação específica de compra, pagamento ou emissão de ingressos.

## Autor

**Nicholas Fernandes**
