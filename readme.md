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

-----

## 💾 Problema 2622: Pessoas Jurídicas

### 📖 Descrição

Este problema, de **nível 1**, exige uma consulta SQL que identifique clientes que são pessoas jurídicas. O objetivo é listar o nome (`name`) de todos os clientes que possuem um registro na tabela `legal_person`, que armazena informações sobre pessoas jurídicas.

### ⚙️ Detalhes das Tabelas

A consulta é executada sobre as tabelas `customers` e `legal_person`, que são unidas por meio de suas chaves primárias e estrangeiras:

  * **customers**:
      * `id` (PK)
      * `name`
  * **legal\_person**:
      * `id` (PK)
      * `id_customers` (FK)

### ✅ Resolução

A solução para este problema utiliza uma junção implícita para combinar as duas tabelas. A cláusula `WHERE` é usada para unir as tabelas com base na igualdade de seus IDs (`C.id = L.id_customers`), garantindo que apenas os clientes que têm um registro correspondente na tabela `legal_person` sejam selecionados.

```sql
SELECT
    C.name
FROM
    customers C, legal_person L
WHERE
    C.id = L.id_customers;
```

### 🏆 Resultado

A submissão da consulta foi **Accepted** (Aceita), demonstrando que a solução está correta e atende aos requisitos do problema.

<img width="719" height="210" alt="Image" src="https://github.com/user-attachments/assets/f55cedb7-9851-4511-bfae-3311c64de397" />

-----

## 💾 Problema 2616: Nenhuma Locação

### 📖 Descrição

Este problema, de **nível 5**, exige uma consulta SQL que identifique clientes que nunca fizeram uma locação. O objetivo é listar o `id` e o `name` de todos os clientes que não possuem um registro correspondente na tabela de locações.

### ⚙️ Detalhes das Tabelas

A consulta é executada sobre as tabelas `customers` e `locations`, que são unidas por meio de suas chaves primárias e estrangeiras:

  * **customers**:
      * `id` (PK)
      * `name`
  * **locations**:
      * `id` (PK)
      * `id_customers` (FK)

### ✅ Resolução

A solução para este problema utiliza um `LEFT JOIN` para combinar a tabela `customers` com a tabela `locations`. O `LEFT JOIN` retorna todos os clientes da tabela `customers` (lado esquerdo) e as locações correspondentes da tabela `locations` (lado direito). Para encontrar os clientes que nunca alugaram, a cláusula `WHERE` é usada para filtrar os resultados onde a coluna `id_customers` da tabela `locations` é `NULL`, o que indica que não houve uma correspondência. A ordenação é feita pelo ID do cliente para garantir a consistência do resultado.

```sql
SELECT
    A.id,
    A.name
FROM
    customers AS A
LEFT JOIN
    locations AS B ON A.id = B.id_customers
WHERE
    B.id_customers IS NULL
ORDER BY
    A.id;
```

### 🏆 Resultado

A submissão da consulta foi **Accepted** (Aceita), demonstrando que a solução está correta e atende aos requisitos do problema.

<img width="724" height="199" alt="Image" src="https://github.com/user-attachments/assets/e5d4ce1a-4d68-447d-8c8c-1d0de0d02501" />

-----

## 💾 Problema 2608: Maior e Menor Preço

### 📖 Descrição

Este problema, de **nível 1**, exige uma consulta SQL de agregação para encontrar o maior e o menor valor de uma coluna. O objetivo é exibir o preço máximo e o preço mínimo da tabela de produtos. As colunas de resultado devem ser nomeadas como `maior_preco` e `menor_preco`, respectivamente.

### ⚙️ Detalhes da Tabela

A consulta é executada sobre a tabela `products`, que possui a seguinte estrutura:

| Coluna | Tipo |
| :--- | :--- |
| `id` (PK) | `numeric` |
| `name` | `varchar` |
| `amount` | `numeric` |
| `price` | `numeric` |

### ✅ Resolução

A solução para este problema utiliza as funções de agregação `MAX()` e `MIN()`. A função `MAX(price)` retorna o maior valor da coluna `price`, e a função `MIN(price)` retorna o menor valor. Ambas as colunas de resultado são renomeadas usando a palavra-chave `AS`.

```sql
SELECT
    MAX(price) AS maior_preco,
    MIN(price) AS menor_preco
FROM
    products;
```

### 🏆 Resultado

A submissão da consulta foi **Accepted** (Aceita), demonstrando que a solução está correta e atende aos requisitos do problema.

<img width="722" height="205" alt="Image" src="https://github.com/user-attachments/assets/3cf8d321-2b16-4e11-99cd-7f18bf1fa037" />

-----

## 💾 Problema 2607: Cidades em Ordem Alfabética

### 📖 Descrição

Este problema, de **nível 1**, exige uma consulta SQL para listar as cidades de forma única e ordenada. O objetivo é exibir todas as cidades distintas da tabela de fornecedores, organizadas em ordem alfabética.

### ⚙️ Detalhes da Tabela

A consulta é executada sobre a tabela `providers`, que possui a seguinte estrutura:

| Coluna | Tipo |
| :--- | :--- |
| `id` (PK) | `numeric` |
| `name` | `varchar` |
| `street` | `varchar` |
| `city` | `varchar` |
| `state` | `char` |

### ✅ Resolução

A solução para este problema utiliza o comando `SELECT` com a palavra-chave `DISTINCT` para garantir que cada cidade apareça apenas uma vez na lista. Em seguida, a cláusula `ORDER BY` é usada para ordenar os resultados em ordem alfabética, com base na coluna `city`.

```sql
SELECT
    DISTINCT city
FROM
    providers
ORDER BY
    city;
```

### 🏆 Resultado

A submissão da consulta foi **Accepted** (Aceita), demonstrando que a solução está correta e atende aos requisitos do problema.

<img width="722" height="209" alt="Image" src="https://github.com/user-attachments/assets/afe642ec-bd55-4f03-b35c-c04c1eb4c41a" />

-----

## 💾 Problema 2615: Expandindo o Negócio

### 📖 Descrição

Este problema, de **nível 1**, exige uma consulta SQL simples. O objetivo é listar todas as cidades onde os clientes da empresa estão localizados. A consulta deve retornar a coluna `city` da tabela `customers`.

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

A solução para este problema é uma consulta `SELECT` direta que seleciona a coluna `city` da tabela `customers`.

```sql
SELECT
    city
FROM
    customers;
```

### 🏆 Resultado

A submissão da consulta foi **Accepted** (Aceita), demonstrando que a solução está correta e atende aos requisitos do problema.

<img width="650" height="185" alt="Image" src="https://github.com/user-attachments/assets/97e6155b-0e4b-40d0-aad7-37561ea536de" />

Com certeza! Com base em todas as atividades, preparei uma conclusão profissional e detalhada, perfeita para a seção de `README.md` de um projeto no GitHub.

---

## Conclusão: Análise e Demonstração de Habilidades em SQL

Este projeto de banco de dados, composto por uma série de desafios de complexidade crescente, serve como uma demonstração prática das minhas habilidades em SQL. Cada atividade foi cuidadosamente selecionada para cobrir um espectro de conceitos essenciais, desde consultas básicas até operações mais avançadas de junção e agregação.

A progressão dos problemas, com base nos níveis de dificuldade, reflete uma metodologia de aprendizado estruturada:

* **Nível 1**: Domínio das consultas fundamentais (`SELECT`, `DISTINCT`), ordenação (`ORDER BY`) e filtragem básica. Esta etapa estabeleceu uma base sólida para a manipulação de dados.
* **Nível 2**: Aplicação de filtros mais complexos (`WHERE` com `OR`) e a introdução de junções de tabelas para resolver problemas que exigem a combinação de dados de fontes distintas.
* **Nível 3**: Aprofundamento nas junções de múltiplas tabelas, permitindo a extração de informações específicas com base em critérios que se estendem por diferentes entidades.
* **Nível 4 e 5**: Resolução de desafios avançados, como a identificação de registros sem correspondência (`LEFT JOIN` com `IS NULL`) e o uso de funções de agregação (`COUNT`, `MAX`, `MIN`) para sumarizar dados, demonstrando a capacidade de realizar análises complexas.

### Resumo das Habilidades Demonstração:

* **Consultas e Filtros**: Habilidade para extrair dados específicos usando `SELECT`, `FROM` e `WHERE`.
* **Agregação**: Competência no uso de funções como `COUNT`, `MAX` e `MIN` para obter insights estatísticos.
* **Junções de Tabelas**: Proficiência na combinação de dados de múltiplas tabelas, utilizando tanto a sintaxe implícita quanto `LEFT JOIN`, para resolver problemas de relacionamento entre entidades.
* **Análise de Dados**: Capacidade de interpretar um problema e traduzi-lo em uma solução SQL eficiente e otimizada.

A finalização bem-sucedida de cada desafio, atestada pelo `Accepted`, valida a precisão das minhas consultas e a compreensão dos conceitos de banco de dados. 