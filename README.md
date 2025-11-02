# 🚀 Board Management System em Java: Estilo Kanban com Arquitetura Avançada

Este projeto demonstra a construção de um **Sistema de Gerenciamento de Tarefas (Kanban Style)**, desenvolvido em Java. O foco está em aplicar **boas práticas de Clean Architecture** e **Design Patterns** na estruturação de camadas, gerenciamento de dados persistentes e tratamento robusto de fluxo de trabalho.

---

## 💡 Destaques da Arquitetura

O sistema é construído sobre uma arquitetura avançada, que separa claramente as responsabilidades, seguindo princípios **SOLID** e um modelo de dados orientado à persistência com JPA.

| Camada | Objetivo Principal | Exemplo de Implementação |
| :--- | :--- | :--- |
| **Service** | Regras de Negócio e Transações | `CardService` gerencia a movimentação e bloqueios de cartões. |
| **Persistence** | Acesso e Persistência de Dados | `BoardDAO` interage com o banco de dados (JPA Entities). |
| **DTO/Entity** | Transferência e Modelo de Domínio | Uso de DTOs para comunicação e Entidades separadas para JPA. |
| **UI** | Interação com Usuário (Console) | `MainMenu` e `BoardMenu` (Interface de Linha de Comando). |

---

## 📋 Funcionalidades Robustas (Flow Control)

O sistema oferece um conjunto completo de operações Kanban e regras de fluxo de trabalho rigorosas:

* ✅ **CRUD Completo:** Criar, visualizar, mover e remover **quadros** e **cartões**.
* 🔁 **Movimentação Controlada:** Mover cartões entre colunas (To Do, Doing, Done, etc.).
* 🚫 **Regras de Bloqueio:** Implementação de regras de fluxo e **tratamento de exceções personalizadas** (`CardBlockedException`, `CardFinishedException`).
* 📦 **Controle de Histórico:** Gerenciamento do histórico de alterações do cartão.
* 🧠 **Interface Interativa:** Menu completo para operações via **Console/CLI**.

---

## 🛠️ Tecnologias e Dependências

* **Linguagem:** Java (versão X.X)
* **Build Tool:** Maven (ou Gradle)
* **Persistência:** JPA / Hibernate
* **Banco de Dados:** (Ex: H2 embutido ou PostgreSQL)
* **Migrations:** Liquibase (para controle de *schema* do banco).

---

## 📂 Estrutura Detalhada do Projeto (Por Pacotes)

| Pacote | Função | Exemplo de Classe |
| :--- | :--- | :--- |
| `controller` | Recebe a requisição da UI e delega a `Service`. | `BoardController` |
| `service` | **Regras de Negócio**. | `CardService`, `BoardQueryService` |
| `persistence.dao` | Abstração do Acesso a Dados. | `BoardDAO`, `CardDAO` |
| `entity` | Modelos de Domínio (`Board`, `Column`, `Card`). | `CardEntity` |
| `dto` | Objetos para Transferência e Apresentação de Dados. | `CardDetailsDTO` |
| `ui` | Componentes de Interação via Console. | `MainMenu.java` |

---

## 📌 Classes Chave (Visão Rápida)

Para uma rápida navegação no código:

* **UI/Entrada:** `Main.java`, `MainMenu.java`
* **Lógica Principal:** `BoardService.java`, `CardService.java`
* **Persistência:** `BoardDAO.java`, `CardDAO.java`
* **Modelo de Dados:** `BoardEntity.java`, `CardEntity.java`
* **Tratamento de Erros:** `CardBlockedException.java`, `EntityNotFoundException.java`

---

## ⚙️ Como Executar o Projeto

### 1. Pré-requisitos

* Java Development Kit (JDK) 17+
* Maven
* Git

### 2. Clonar e Configurar

```bash
# O comando abaixo clonará o repositório
git clone [https://github.com/BruninhaG/java-kanban-task-manager]
cd java-kanban-task-manager
```

- **Configuração de BD**: Verifique o arquivo de configuração (ex: application.properties) para ajustar as credenciais do banco de dados, se necessário.

### 3. Build e Execução (Console)
# Compila e instala as dependências
mvn clean install

# Executa a aplicação via terminal (substitua a classe principal se necessário)
mvn exec:java -Dexec.mainClass="br.com.dio.Main"

## 👩‍💻 Autora
Feito com 💛 por Bruna Guimarães

## 🌟 Apoie o projeto

Se você gostou, não esqueça de deixar uma ⭐ no repositório!
Isso ajuda muito o projeto a crescer e me incentiva a continuar criando. 🙌
