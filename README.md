﻿# Board-de-tarefas
# 🧠 Muslim Task Board Manager

Bem-vindo ao **Muslim Task Board Manager**, um sistema completo de gerenciamento de tarefas com foco em clareza, robustez e extensibilidade. Este projeto foi desenvolvido com Java puro, JDBC, Liquibase e uma interface de linha de comando amigável.

---

## 📦 Estrutura do Projeto

| Camada | Descrição | Exemplos |
|--------|-----------|----------|
| **DTOs** | Transporte seguro e leve de dados | `BoardDetailDTO`, `CardDetailsDTO` |
| **Entidades** | Representação do domínio | `BoardEntity`, `CardEntity`, `BlockEntity` |
| **DAOs** | Acesso direto ao banco via JDBC | `BoardDAO`, `CardDAO`, `BlockDAO` |
| **Serviços** | Lógica de negócio com validações e transações | `CardService`, `BoardService` |
| **UI CLI** | Interface de linha de comando | `MainMenu`, `BoardMenu` |
| **Migração** | Evolução do banco com versionamento | Liquibase + changelogs SQL |

---

## 🗃️ Estrutura de Banco de Dados

- **boards**: Quadro principal
- **boards_columns**: Colunas do quadro (ex: Inicial, Pendente, Finalizado, Cancelado)
- **cards**: Tarefas vinculadas às colunas
- **blocks**: Histórico de bloqueios com timestamps e razões

🔗 Relacionamentos com `ON DELETE CASCADE` garantem integridade e limpeza automática.

---

## 🚀 Funcionalidades

- Criar boards com colunas personalizadas
- Criar, mover, bloquear, desbloquear e cancelar cards
- Visualizar cards, colunas e boards com contagem de tarefas
- Migração automática do banco com Liquibase
- Interface interativa via terminal

---

## 🧠 Lógica de Negócio Inteligente

- Cards não podem ser movidos se estiverem bloqueados
- Cards finalizados não podem ser alterados
- Bloqueios e desbloqueios são registrados com motivo e horário
- Validações robustas com exceções personalizadas (`CardBlockedException`, `CardFinishedException`, etc.)

---

## 🔮 Melhorias Futuras

| 💡 Ideia | Descrição |
|---------|-----------|
| 🌐 API REST | Expor os serviços via Spring Boot para integração com front-end |
| 🖼️ Interface Gráfica | Migrar para JavaFX ou Swing para uma experiência visual |
| 📊 Relatórios | Gerar estatísticas de produtividade, bloqueios e movimentações |
| 🔐 Multiusuário | Permitir autenticação e boards por usuário |
| 🧪 Testes Automatizados | Usar JUnit e banco H2 para validar regras de negócio |
| 📁 Exportação | Gerar `.txt` ou `.csv` com os dados do board e seus cards |

---

## ✨ Destaques Técnicos

- Uso de `Lombok` para reduzir boilerplate
- Transações manuais com `commit()` e `rollback()` para segurança
- Conversores utilitários (`OffsetDateTimeConverter`) para compatibilidade temporal
- Scanner com validações para entrada segura na CLI

---

## 🙌 Conclusão

Este projeto é uma base sólida para qualquer sistema de gerenciamento de tarefas. Ele combina clareza arquitetural com controle total sobre o fluxo de dados e regras de negócio. Com algumas evoluções, pode se tornar uma aplicação web completa ou até um produto comercial.
