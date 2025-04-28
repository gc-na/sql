<!--
Meta Description: # CALL: Como Utilizar o Comando CALL em SQL ## Sinopse O comando `CALL` em SQL é utilizado para invocar procedimentos armazenados, permitindo a execuç...
Meta Keywords: call, procedimento, sql, comando, execução
-->

# CALL: Como Utilizar o Comando CALL em SQL

## Sinopse
O comando `CALL` em SQL é utilizado para invocar procedimentos armazenados, permitindo a execução de blocos de código que encapsulam lógica de negócios complexa. É uma ferramenta poderosa para otimização de consultas e operações no banco de dados.

## Documentação
O comando `CALL` é um recurso disponível em diversos sistemas de gerenciamento de banco de dados (SGBDs) que suportam procedimentos armazenados, como MySQL, PostgreSQL e SQL Server. Ele permite a execução de um procedimento previamente definido no banco de dados.

### Propósito
O principal objetivo do `CALL` é facilitar a execução de rotinas complexas e reutilizáveis, promovendo a modularidade e a manutenção do código SQL.

### Uso
A sintaxe básica do comando `CALL` é a seguinte:

```sql
CALL nome_do_procedimento(parametros);
```

- `nome_do_procedimento`: o nome do procedimento armazenado que você deseja invocar.
- `parametros`: uma lista opcional de parâmetros que serão passados para o procedimento.

### Detalhes
- O uso de `CALL` pode variar dependendo do SGBD. Por exemplo, no MySQL, os procedimentos podem ter parâmetros de entrada e saída, enquanto no PostgreSQL, a sintaxe pode ser ligeiramente diferente.
- É importante garantir que o procedimento exista e tenha os tipos de parâmetros corretos ao utilizar o `CALL`.

## Exemplos
### Exemplo 1: Chamada Simples de um Procedimento
```sql
CALL atualiza_estoque(123, 10);
```
Neste exemplo, o procedimento `atualiza_estoque` é chamado, passando dois parâmetros: o ID do produto e a quantidade a ser atualizada.

### Exemplo 2: Chamada de um Procedimento com Retorno
```sql
CALL calcula_salario(456, @salario_final);
SELECT @salario_final;
```
Aqui, o procedimento `calcula_salario` é invocado, e o resultado é armazenado em uma variável.

## Explicação
Ao utilizar o comando `CALL`, é fundamental estar atento a alguns pontos:

- **Parâmetros Incorretos**: Passar parâmetros com tipos incompatíveis pode resultar em erros de execução. Verifique sempre os tipos esperados.
- **Procedimentos Não Encontrados**: Tentar chamar um procedimento que não exista gerará um erro. Verifique a existência do procedimento antes de chamá-lo.
- **Transações**: Dependendo do SGBD e da lógica do procedimento, as operações podem estar sujeitas a transações. Certifique-se de entender como isso afeta a execução do seu código.

## Resumo em Uma Frase
O comando `CALL` em SQL é usado para invocar procedimentos armazenados, facilitando a execução de lógica complexa no banco de dados.