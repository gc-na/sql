<!--
Meta Description: # Comando INSERT em SQL: Como Inserir Dados em Tabelas ## Sinopse O comando `INSERT` em SQL é utilizado para adicionar novos registros a uma tabela em...
Meta Keywords: insert, inserir, uma, dados, sql
-->

# Comando INSERT em SQL: Como Inserir Dados em Tabelas

## Sinopse
O comando `INSERT` em SQL é utilizado para adicionar novos registros a uma tabela em um banco de dados. Essa operação é fundamental para a manipulação de dados em sistemas de gerenciamento de banco de dados.

## Documentação
O comando `INSERT` permite inserir uma ou mais linhas de dados em uma tabela. Ele pode ser utilizado em diferentes formas, dependendo da necessidade do usuário e da estrutura da tabela.

### Estrutura Básica
A sintaxe básica do comando `INSERT` é a seguinte:

```sql
INSERT INTO nome_da_tabela (coluna1, coluna2, coluna3, ...)
VALUES (valor1, valor2, valor3, ...);
```

- `nome_da_tabela`: Nome da tabela onde os dados serão inseridos.
- `coluna1, coluna2, ...`: Nomes das colunas nas quais os valores serão inseridos.
- `valor1, valor2, ...`: Valores a serem inseridos nas respectivas colunas.

### Inserir Várias Linhas
É possível inserir várias linhas em uma única instrução `INSERT`:

```sql
INSERT INTO nome_da_tabela (coluna1, coluna2)
VALUES (valor1a, valor2a),
       (valor1b, valor2b),
       (valor1c, valor2c);
```

### Inserir sem Especificar Colunas
Caso você deseje inserir valores em todas as colunas da tabela, é possível omitir a lista de colunas:

```sql
INSERT INTO nome_da_tabela
VALUES (valor1, valor2, valor3, ...);
```

Neste caso, a ordem dos valores deve corresponder à ordem das colunas definidas na tabela.

## Exemplos
### Exemplo 1: Inserir uma linha
```sql
INSERT INTO clientes (nome, email, idade)
VALUES ('João Silva', 'joao.silva@email.com', 30);
```

### Exemplo 2: Inserir várias linhas
```sql
INSERT INTO produtos (nome, preco)
VALUES ('Produto A', 10.00),
       ('Produto B', 15.50),
       ('Produto C', 7.20);
```

### Exemplo 3: Inserir sem especificar colunas
```sql
INSERT INTO funcionarios
VALUES (1, 'Maria Souza', 'Analista', 4000);
```

## Explicação
Embora o comando `INSERT` seja bastante simples, alguns pontos devem ser observados:

- **Chaves Primárias**: Se a tabela possui uma coluna de chave primária, o valor para essa coluna deve ser único. Tentar inserir um valor duplicado resultará em um erro.
- **Valores Nulos**: Se uma coluna não permite valores nulos e você não fornecer um valor para ela, ocorrerá um erro.
- **Tipos de Dados**: Os valores fornecidos devem ser compatíveis com os tipos de dados das colunas. Por exemplo, não se pode inserir um texto em uma coluna que espera um número.
- **Transações**: Em sistemas que suportam transações, o comando `INSERT` pode ser incluído em uma transação para garantir a atomicidade das operações.

## Resumo em Uma Linha
O comando `INSERT` em SQL é utilizado para adicionar novos registros a uma tabela, permitindo a manipulação eficiente de dados em bancos de dados.