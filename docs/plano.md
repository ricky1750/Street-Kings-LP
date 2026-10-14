# Plano do Projeto - Street Kings

## Elementos do grupo

| Elemento | Sigla |
|----------|-------|
| Nome Apelido (n.º 00) | A |
| Nome Apelido (n.º 00) | B |
| Nome Apelido (n.º 00) | C |

## Divisão de tarefas

| Funcionalidade | Responsável | Apoio |
|----------------------------------------------------|-------------|-------|
| Base de dados (`database.sql`, ligação, queries) | A | C |
| Registo, login, logout, alterar dados/palavra-passe (hash) | A | B |
| Criação de piloto, níveis e experiência | B | A |
| Loja, inventário e transações | C | B |
| Missões | B | C |
| Corridas (combate) e rivais | C | A |
| Ranking e histórico | A | B |
| Área de administração | B | A |
| Validação de dados e tratamento de erros | A | todos |
| Testes (pytest) | todos | - |
| README e documentação | todos | - |
| Apresentação | todos | - |

Cada funcionalidade tem uma issue no GitHub atribuída ao responsável. O apoio revê o código.

## Calendário

Ajustar as datas às datas do Classroom.

| Semana | Objetivo | Entrega |
|--------|----------|---------|
| 1 | Repositório, estrutura, `jogo.md`, modelo ER, plano, issues | **1.ª entrega** (tag `entrega-1`) |
| 2 | Base de dados (tabelas e dados iniciais), ligação em Python, classes `Utilizador` e `Personagem` | - |
| 3 | Registo/login com hash, criação de piloto, níveis e XP, menus principais | - |
| 4 | Loja, inventário, transações e histórico | - |
| 5 | Corridas, rivais e missões | - |
| 6 | Ranking, área de administração, validação e tratamento de erros | - |
| 7 | Testes, correção de erros, README completo | - |
| 8 | Ensaio da apresentação e entrega final | Entrega final |

## Regras de trabalho

- Antes de começar: `git pull`. No fim: `git add`, `git commit`, `git push`.
- Uma branch por funcionalidade (`feature/login`, `feature/loja`, `feature/corridas`, ...), juntada à `main` quando estiver a funcionar.
- Mensagens de commit claras (exemplo: `Adiciona validação de username no registo`).
- Ninguém envia para a `main` código que não corre.
- Reunião curta no início de cada semana para ver o que falta.
