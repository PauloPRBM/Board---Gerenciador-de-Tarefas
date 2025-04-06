## Board Gerenciador de Tarefas

## Projeto desenvolvido para o Bootcamp DecolaTech da Avanade 2025, em parceria com Dio.

# 🗂️ Projeto de Board - Gerenciador de Tarefas

Este projeto tem como objetivo desenvolver um sistema de **board customizável** para **acompanhamento e gerenciamento de tarefas**, permitindo a criação de quadros com colunas específicas e movimentação de cards (tarefas) conforme regras de fluxo.

---

## 🚀 Funcionalidades Principais

- 📋 Criar novos boards com colunas customizadas
- 📂 Salvar e carregar boards no banco de dados NoSQL
- ➕ Adicionar cards (tarefas) com título, descrição e data
- 🔄 Mover cards entre colunas seguindo regras de fluxo
- ⛔ Bloquear/desbloquear cards com justificativa
- 🕒 Armazenar histórico de movimentações e bloqueios
- 📊 Gerar relatórios de tempo e de bloqueios

---

## ⚙️ Requisitos do Sistema

### 🔧 Funcionalidades obrigatórias

- Menu inicial com:
  - Criar novo board
  - Selecionar board
  - Excluir board
- Banco de dados NoSQL para persistência

### 📐 Regras dos Boards

- Um board possui:
  - Nome
  - Mínimo de **3 colunas**
- Cada coluna tem:
  - Nome, ordem no board e tipo: `Inicial`, `Cancelamento`, `Final`, `Pendente`
  - Só pode haver:
    - 1 coluna do tipo `Inicial`
    - 1 do tipo `Cancelamento`
    - 1 do tipo `Final`
    - N do tipo `Pendente`
- Cada coluna pode conter 0 ou mais cards
- Cada card possui:
  - Título, descrição, data de criação, status de bloqueio
  - Um **card bloqueado não pode ser movido**
  - Para bloquear/desbloquear é obrigatório informar um motivo
  - Card deve seguir a ordem das colunas (exceto se for cancelado)

### 🧪 Funcionalidades opcionais

- Armazenar data/hora de entrada e saída em cada coluna
- Gerar relatórios de tempo por tarefa
- Gerar relatórios de bloqueios

---

## 🎯 Diagrama de Casos de Uso

```mermaid
graph TD
    Usuario -->|Cria| Board
    Usuario -->|Seleciona| Board
    Usuario -->|Exclui| Board
    Usuario -->|Cria| Coluna
    Usuario -->|Adiciona| Card
    Usuario -->|Move| Card
    Usuario -->|Bloqueia| Card
    Usuario -->|Desbloqueia| Card
    Usuario -->|Gera| RelatorioTempo
    Usuario -->|Gera| RelatorioBloqueios
    Board --> Coluna
    Coluna --> Card
