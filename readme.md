# Atividade SQL - BeeCrowd

## Descrição
Esta atividade consiste na resolução de exercícios de SQL da plataforma [BeeCrowd](https://www.beecrowd.com.br/). O objetivo é praticar consultas, manipulação de dados e compreensão de bancos de dados relacionais, aplicando comandos SQL como `SELECT`, `JOIN`, `GROUP BY`, `ORDER BY`, entre outros.

## Observações
- Todas as queries foram testadas exclusivamente no BeeCrowd.
- Para uma visualização alternativa, acesse este [link no Notion](https://speckled-driver-678.notion.site/ATIVIDADE-SQL-BEECROWD-2564a2e1b1b2809093abee563b4c6442?source=copy_link).


---

## Requisitos
- Conhecimento básico de SQL (comandos `SELECT`, `INSERT`, `UPDATE`, `DELETE`)
- Entendimento de tabelas, colunas e relacionamentos
- Banco de dados MySQL, PostgreSQL ou equivalente para testar as queries

---

# ----------------------------------------------------------------------------------------- #


## 💾 Problema 2602: Select Básico

### 📖 Descrição

Este problema, de **nível 4**, exige uma consulta SQL simples para selecionar informações de uma tabela específica. O objetivo é exibir o nome de todos os clientes que estão cadastrados no estado do Rio Grande do Sul ('RS').

### ⚙️ Detalhes da Tabela

A consulta é executada sobre a tabela `customers`, que possui a seguinte estrutura:

| Coluna | Tipo |
| :--- | :--- |
| `id` (PK) | `numeric` |
| `name` | `varchar` |
| `street` | `varchar` |
| `city` | `varchar` |
| `state` | `char` |
| `credit_limit` | `numeric` |

### ✅ Resolução

A solução para este problema é uma consulta `SELECT` básica que filtra os resultados com a cláusula `WHERE`, garantindo que apenas os clientes do estado 'RS' sejam exibidos.

```sql
SELECT
    name
FROM
    customers
WHERE
    state = 'RS';
```

### 🏆 Resultado

A submissão da consulta foi **Accepted** (Aceita), demonstrando que a solução está correta e atende aos requisitos do problema.

-----

