<!--
Meta Description: # MERGE: Comando SQL para Inserção e Atualização Eficiente de Dados ## Sinopse O comando SQL `MERGE` é utilizado para realizar operações de atualizaçã...
Meta Keywords: origem, merge, dados, uma, tabela
-->

# MERGE: Comando SQL para Inserção e Atualização Eficiente de Dados

## Sinopse
O comando SQL `MERGE` é utilizado para realizar operações de atualização e inserção em uma tabela de forma eficiente, combinando dados de uma tabela de origem com uma tabela de destino em uma única instrução.

## Documentação
O `MERGE` é um comando poderoso que permite que os desenvolvedores e administradores de banco de dados realizem operações complexas de manipulação de dados. Ele é especialmente útil em cenários onde é necessário sincronizar dados entre duas tabelas, evitando a necessidade de escrever múltiplas instruções `INSERT`, `UPDATE` e `DELETE`.

### Propósito
O propósito do `MERGE` é simplificar a lógica de inserção e atualização de registros em uma única operação. Ele é especialmente valioso para operações de ETL (Extração, Transformação e Carga) e quando se trabalha com dados que precisam ser atualizados ou inseridos com base em condições específicas.

### Uso
A sintaxe básica do comando `MERGE` é a seguinte:

```sql
MERGE INTO tabela_destino AS alvo
USING tabela_origem AS origem
ON condição_de_igualdade
WHEN MATCHED THEN
    UPDATE SET alvo.coluna1 = origem.coluna1, alvo.coluna2 = origem.coluna2
WHEN NOT MATCHED THEN
    INSERT (coluna1, coluna2) VALUES (origem.coluna1, origem.coluna2);
```

- **tabela_destino**: a tabela onde os dados serão atualizados ou inseridos.
- **tabela_origem**: a tabela que contém os dados que serão utilizados para a operação.
- **condição_de_igualdade**: a condição que determina como os registros das duas tabelas se correspondem.
- **WHEN MATCHED**: especifica a ação a ser realizada se um registro correspondente for encontrado.
- **WHEN NOT MATCHED**: especifica a ação a ser realizada se não houver um registro correspondente.

## Exemplos
### Exemplo 1: Atualizando e Inserindo Dados
Suponha que você tenha uma tabela de clientes e uma tabela de atualizações. O seguinte comando `MERGE` atualiza informações de clientes existentes e insere novos clientes:

```sql
MERGE INTO clientes AS alvo
USING atualizacoes AS origem
ON alvo.id_cliente = origem.id_cliente
WHEN MATCHED THEN
    UPDATE SET alvo.nome = origem.nome, alvo.email = origem.email
WHEN NOT MATCHED THEN
    INSERT (id_cliente, nome, email) VALUES (origem.id_cliente, origem.nome, origem.email);
```

### Exemplo 2: Removendo Registros
Você também pode usar o `MERGE` para remover registros que não estão mais presentes na tabela de origem:

```sql
MERGE INTO produtos AS alvo
USING produtos_novos AS origem
ON alvo.id_produto = origem.id_produto
WHEN NOT MATCHED BY SOURCE THEN
    DELETE;
```

## Explicação
### Armadilhas e Observações Comuns
1. **Condições de Igualdade**: É crucial garantir que a condição de igualdade seja precisa para evitar atualizações indesejadas.
2. **Desempenho**: Embora o `MERGE` possa otimizar operações, em casos de grandes conjuntos de dados, o desempenho deve ser avaliado, pois a complexidade da consulta pode impactar o tempo de execução.
3. **Transações**: O `MERGE` é tratado como uma transação única, o que significa que se ocorrer um erro durante a execução, nenhuma alteração será aplicada.
4. **Compatibilidade**: A sintaxe e o suporte ao `MERGE` podem variar entre diferentes sistemas de gerenciamento de banco de dados (SGBDs), como SQL Server, Oracle, PostgreSQL, entre outros.

## Resumo em Uma Linha
O comando SQL `MERGE` permite a atualização e inserção de dados em uma tabela de forma eficiente, sincronizando dados de uma tabela de origem com uma tabela de destino.