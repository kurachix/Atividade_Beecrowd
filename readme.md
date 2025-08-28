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

<img width="738" height="219" alt="Image" src="https://github.com/user-attachments/assets/f6abc6cb-054c-4926-8069-561fa5b2a871" />

-----
-----

## 💾 Problema 2603: Endereço dos Clientes

### 📖 Descrição

Este problema, de **nível 1**, exige uma consulta SQL para selecionar o nome e o endereço dos clientes de uma cidade específica. O objetivo é exibir o nome (`name`) e a rua (`street`) de todos os clientes que estão cadastrados na cidade de 'Porto Alegre'.

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

A solução para este problema é uma consulta `SELECT` que seleciona as colunas `name` e `street`, aplicando um alias para a tabela `customers` (`AS A`). A cláusula `WHERE` é utilizada para filtrar os resultados, exibindo apenas os clientes da cidade de 'Porto Alegre'.

```sql
SELECT
    A.name as name,
    A.street as street
FROM
    customers as A
WHERE
    city = 'Porto Alegre';
```

### 🏆 Resultado

A submissão da consulta foi **Accepted** (Aceita), demonstrando que a solução está correta e atende aos requisitos do problema.

<img width="723" height="205" alt="Image" src="https://github.com/user-attachments/assets/a0808d11-23c1-42fa-a694-e77f6bc3bd84" />

Com certeza\! Aqui está a atividade de banco de dados, formatada em **Markdown**, focada exclusivamente no problema 2604, ideal para um `README.md` no GitHub.

-----

## 💾 Problema 2604: Menores que 10 ou Maiores que 100

### 📖 Descrição

Este problema, de **nível 2**, exige uma consulta SQL que selecione produtos com base em sua faixa de preço. O objetivo é exibir o `id` e o `name` de todos os produtos cujo preço (`price`) seja menor que 10 **ou** maior que 100.

### ⚙️ Detalhes da Tabela

A consulta é executada sobre a tabela `products`, que possui a seguinte estrutura:

| Coluna | Tipo |
| :--- | :--- |
| `id` (PK) | `numeric` |
| `name` | `varchar` |
| `amount` | `numeric` |
| `price` | `numeric` |

### ✅ Resolução

A solução para este problema é uma consulta `SELECT` que seleciona as colunas `id` e `name`, aplicando um alias para a tabela `products` (`AS A`). A cláusula `WHERE` é utilizada com o operador lógico `OR` para filtrar os resultados que atendem a uma das duas condições: preço maior que 100 ou preço menor que 10.

```sql
SELECT
    A.id as id,
    A.name as name
FROM
    products as A
WHERE
    price > 100 or price < 10;
```

### 🏆 Resultado

A submissão da consulta foi **Accepted** (Aceita), demonstrando que a solução está correta e atende aos requisitos do problema.

<img width="721" height="202" alt="Image" src="https://github.com/user-attachments/assets/646a530f-1925-4574-b393-e96b37ba2885" />
