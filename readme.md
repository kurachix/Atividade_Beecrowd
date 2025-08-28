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

-----

## 💾 Problema 2618: Produtos Importados

### 📖 Descrição

Este problema, de **nível 3**, exige uma consulta SQL mais complexa, envolvendo múltiplas tabelas. O objetivo é listar os produtos que atendem a duas condições específicas:

1.  O produto deve ser fornecido pela empresa `'Sansul SA'`.
2.  O produto deve pertencer à categoria `'Imported'`.

A consulta deve retornar o nome do produto, o nome do fornecedor e o nome da categoria.

### ⚙️ Detalhes das Tabelas

A consulta é executada sobre três tabelas, que são unidas por meio de suas chaves primárias e estrangeiras:

  * **products**:
      * `id` (PK)
      * `name`
      * `id_providers` (FK)
      * `id_categories` (FK)
  * **providers**:
      * `id` (PK)
      * `name`
  * **categories**:
      * `id` (PK)
      * `name`

### ✅ Resolução

A solução para este problema utiliza a cláusula `JOIN` implícita, listando as três tabelas no `FROM` e definindo as condições de junção no `WHERE`. Aliases (`A`, `B`, `C`) são usados para simplificar a escrita da consulta. As condições de filtro para o nome do fornecedor e da categoria também são adicionadas na cláusula `WHERE`.

```sql
SELECT
    A.name AS product_name,
    B.name AS provider_name,
    C.name AS category_name
FROM
    products A, providers B, categories C
WHERE
    A.id_providers = B.id
    AND A.id_categories = C.id
    AND B.name = 'Sansul SA'
    AND C.name = 'Imported';
```

### 🏆 Resultado

A submissão da consulta foi **Accepted** (Aceita), demonstrando que a solução está correta e atende aos requisitos do problema.

<img width="722" height="208" alt="Image" src="https://github.com/user-attachments/assets/f0cea29a-65b1-49e2-bcce-cbda319213dc" />

-----

## 💾 Problema 2624: Quantidades de Cidades por Clientes

### 📖 Descrição

Este problema, de **nível 3**, exige uma consulta SQL de agregação. O objetivo é contar o número de cidades distintas onde os clientes estão localizados. A consulta deve retornar uma única coluna com a contagem total, nomeada como `count`.

### ⚙️ Detalhes da Tabela

A consulta é executada sobre a tabela `Customers`, que possui a seguinte estrutura:

| Coluna | Tipo |
| :--- | :--- |
| `id` (PK) | `numeric` |
| `name` | `varchar` |
| `street` | `varchar` |
| `city` | `varchar` |
| `state` | `char` |
| `credit_limit` | `numeric` |

### ✅ Resolução

A solução para este problema utiliza a função de agregação `COUNT()` junto com a palavra-chave `DISTINCT`. A função `COUNT(DISTINCT city)` garante que cada cidade seja contada apenas uma vez, mesmo que haja múltiplos clientes na mesma cidade. O resultado é renomeado para `count` usando o alias `AS`.

```sql
SELECT
    COUNT(DISTINCT city) AS count
FROM
    Customers;
```

### 🏆 Resultado

A submissão da consulta foi **Accepted** (Aceita), demonstrando que a solução está correta e atende aos requisitos do problema.

<img width="724" height="206" alt="Image" src="https://github.com/user-attachments/assets/3093d810-5921-4851-bfc1-b7c9b95d2dce" />

-----

## 💾 Problema 2613: Filmes em Promoção

### 📖 Descrição

Este problema, de **nível 2**, exige uma consulta SQL que combine informações de duas tabelas diferentes. O objetivo é listar o `id` e o `name` de todos os filmes que estão em promoção, ou seja, cujo valor de aluguel é menor que 2.00.

### ⚙️ Detalhes das Tabelas

A consulta é executada sobre as tabelas `prices` e `movies`, que são unidas por meio de suas chaves primárias e estrangeiras:

  * **prices**:
      * `id` (PK)
      * `name`
      * `value`
  * **movies**:
      * `id` (PK)
      * `name`
      * `id_prices` (FK)

### ✅ Resolução

A solução para este problema utiliza uma junção implícita para combinar as duas tabelas. A cláusula `WHERE` é usada para unir as tabelas (`B.id_prices = A.id`) e, em seguida, filtrar os resultados com base no valor do aluguel (`A.value < 2.00`).

```sql
SELECT
    B.id,
    B.name
FROM
    prices AS A,
    movies AS B
WHERE
    B.id_prices = A.id
AND A.value < 2.00;
```

### 🏆 Resultado

A submissão da consulta foi **Accepted** (Aceita), demonstrando que a solução está correta e atende aos requisitos do problema.

<img width="723" height="206" alt="Image" src="https://github.com/user-attachments/assets/16f12f35-2eec-4c6b-91b1-ad94a49d5d6a" />


