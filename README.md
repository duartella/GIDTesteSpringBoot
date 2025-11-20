# GIDTesteSpringBoot

## 🛠️ Visão Geral do Projeto

Este projeto é uma aplicação *backend* desenvolvida com **Spring Boot**, utilizando **Java** como linguagem principal. O objetivo é fornecer uma estrutura de teste/exemplo para o desenvolvimento de serviços RESTful. O projeto emprega **Gradle** como sistema de *build* e utiliza o **SQLite** para persistência de dados local, configurado para facilitar a execução e testes em ambientes de desenvolvimento.

É imperativo que você mantenha a documentação dos *endpoints* e a estrutura de classes alinhada com as funcionalidades reais da aplicação, que aqui não estão detalhadas.

## ⚙️ Tecnologias Utilizadas

A pilha tecnológica deste repositório é composta por:

  * **Linguagem de Programação:** Java (Recomendado: **JDK 21+**)
  * **Framework Principal:** Spring Boot (Recomendado: Versão estável)
  * **Gerenciador de Dependências:** Gradle
  * **Banco de Dados:** SQLite (Configurado via H2/Hibernate para uso com arquivo local)

## 📋 Pré-requisitos

Para que a aplicação compile e execute corretamente em seu ambiente, você deve possuir o seguinte instalado:

1.  **Java Development Kit (JDK):** Versão 21 ou superior.
2.  **Sistema de Controle de Versão (VCS):** Git.
3.  **Ferramenta de Linha de Comando:** Acesso a um terminal com suporte a *shell scripts* (`.sh`) para o *wrapper* do Gradle.

## 🚀 Configuração e Instalação

Siga o procedimento estrito abaixo para clonar, configurar e preparar o *build* do projeto:

### 1\. Clonagem

Utilize o terminal para clonar o repositório.

```bash
git clone https://github.com/duartella/GIDTesteSpringBoot.git
cd GIDTesteSpringBoot
```

### 2\. Configuração do Banco de Dados SQLite

O projeto utiliza o **SQLite** para armazenamento local.

  * O arquivo de banco de dados (`.db`) será criado automaticamente ou referenciado no caminho definido no arquivo `src/main/resources/application.properties` ou `application.yml`.
  * **Atenção:** Garanta que a configuração do *driver* JDBC e o Dialeto do Hibernate para SQLite estejam implementados e mapeados corretamente na sua configuração do Spring. Falhas de conexão são geralmente atribuídas a caminhos de arquivo incorretos ou dependências não resolvidas.

### 3\. Build do Projeto

Execute o comando do **Gradle** para resolver todas as dependências e compilar o projeto. Isso também executará quaisquer testes unitários definidos.

```bash
./gradlew clean build
```

*(No Windows, você pode precisar usar `gradlew clean build`)*

## ▶️ Execução da Aplicação

Após o *build* ser concluído **sem erros**, a aplicação está pronta para ser iniciada.

### Opção 1: Execução Direta via Gradle

Esta é a maneira mais rápida para fins de desenvolvimento:

```bash
./gradlew bootRun
```

### Opção 2: Execução do JAR Empacotado

Gere o arquivo JAR executável e inicie-o.

```bash
java -jar build/libs/GIDTesteSpringBoot-*.jar
```

A aplicação será iniciada e estará disponível no endereço `http://localhost:8080`, ou na porta especificada na sua configuração do Spring.

## 📡 Endpoints da API (Modelo)

**AVISO SEVERO:** Esta seção é **mandatória** para a usabilidade e deve ser detalhada por você para refletir **exatamente** os *endpoints* implementados em seus controladores Spring (`@RestController`).

O modelo a seguir representa a estrutura esperada para a documentação da sua API:

| Método HTTP | Endpoint | Descrição |
| :--- | :--- | :--- |
| `GET` | `/api/v1/nome-do-recurso` | Retorna uma lista paginada de todos os recursos. |
| `GET` | `/api/v1/nome-do-recurso/{id}` | Recupera um recurso específico pelo ID. |
| `POST` | `/api/v1/nome-do-recurso` | Cria uma nova instância do recurso. **Corpo:** JSON de entidade. |
| `PUT` | `/api/v1/nome-do-recurso/{id}` | Atualiza completamente um recurso existente. |
| `DELETE` | `/api/v1/nome-do-recurso/{id}` | Remove um recurso específico. |

