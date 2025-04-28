<!--
Meta Description: # SAVEPOINT: Controle de Transações em SQL ## Sinopse O comando **SAVEPOINT** em SQL permite que os desenvolvedores criem pontos de salvamento dentro ...
Meta Keywords: savepoint, transação, que, uma, sql
-->

# SAVEPOINT: Controle de Transações em SQL

## Sinopse
O comando **SAVEPOINT** em SQL permite que os desenvolvedores criem pontos de salvamento dentro de uma transação, possibilitando reverter partes específicas da transação sem afetar todo o processo. Isso é especialmente útil para garantir a integridade dos dados e facilitar o gerenciamento de erros.

## Documentação
O **SAVEPOINT** é uma instrução SQL que define um ponto de salvamento em uma transação. Este comando é útil quando você deseja dividir uma transação em partes menores, permitindo que você reverta a transação até o ponto de salvamento, em vez de reverter toda a transação caso ocorra um erro.

### Propósito
- Criar um ponto de referência dentro de uma transação.
- Permitir reverter operações até um ponto específico, sem descartar todas as modificações realizadas.

### Uso
A sintaxe básica do comando SAVEPOINT é a seguinte:

```sql
SAVEPOINT nome_do_savepoint;
```

Onde `nome_do_savepoint` é um identificador que você escolhe para o ponto de salvamento. Uma vez que um SAVEPOINT é definido, você pode usar o comando **ROLLBACK TO** para reverter a transação até esse ponto.

### Detalhes
- O SAVEPOINT é utilizado apenas dentro de transações.
- Você pode ter múltiplos SAVEPOINTs em uma única transação.
- O ponto de salvamento não é persistente; ele é descartado assim que a transação é confirmada (COMMIT) ou revertida (ROLLBACK).
- O uso excessivo de SAVEPOINTs pode tornar a lógica de transações mais complexa, portanto, é importante usá-los com sabedoria.

## Exemplos
### Exemplo 1: Criando e reverter para um SAVEPOINT

```sql
BEGIN;

INSERT INTO funcionarios (nome, cargo) VALUES ('Ana', 'Gerente');
SAVEPOINT antes_da_atualizacao;

INSERT INTO funcionarios (nome, cargo) VALUES ('Bruno', 'Analista');
ROLLBACK TO antes_da_atualizacao;  -- Reverte apenas a inserção de Bruno

COMMIT;  -- Confirma apenas a inserção de Ana
```

### Exemplo 2: Múltiplos SAVEPOINTs

```sql
BEGIN;

INSERT INTO produtos (nome, preco) VALUES ('Produto A', 10.00);
SAVEPOINT ponto1;

INSERT INTO produtos (nome, preco) VALUES ('Produto B', 15.00);
SAVEPOINT ponto2;

INSERT INTO produtos (nome, preco) VALUES ('Produto C', 20.00);
ROLLBACK TO ponto1;  -- Reverte até o primeiro SAVEPOINT

COMMIT;  -- Confirma apenas a inserção do Produto A
```

## Explicação
Um erro comum ao usar SAVEPOINT é não entender que ele não interrompe a transação, mas apenas a marca. Além disso, se um ROLLBACK for executado sem especificar um SAVEPOINT, toda a transação será revertida. É importante também lembrar que, após um COMMIT, todos os SAVEPOINTs são perdidos e não podem ser utilizados novamente.

## Resumo em Uma Linha
O comando SAVEPOINT em SQL permite criar pontos de salvamento em transações, possibilitando reverter operações específicas sem descartar toda a transação.