<!--
Meta Description: # DECLARE em SQL: Comando Essencial para Definindo Variáveis ## Sinopse O comando `DECLARE` em SQL é utilizado para definir variáveis que podem armaze...
Meta Keywords: declare, sql, que, comando, para
-->

# DECLARE em SQL: Comando Essencial para Definindo Variáveis

## Sinopse
O comando `DECLARE` em SQL é utilizado para definir variáveis que podem armazenar dados temporários durante a execução de um bloco de código, como uma stored procedure ou um bloco anônimo. Este comando é crucial para manipulação de dados e controle de fluxo em consultas SQL.

## Documentação
O comando `DECLARE` permite que os desenvolvedores de banco de dados criem variáveis que podem ser usadas para armazenar valores temporários. Estas variáveis são úteis em stored procedures, funções e scripts SQL, permitindo que os programadores armazenem resultados intermediários ou parâmetros de entrada.

### Propósito
- Armazenar valores temporários.
- Facilitar operações em loops e condicionais.
- Melhorar a legibilidade e manutenção do código.

### Uso
A sintaxe básica para o comando `DECLARE` é a seguinte:

```sql
DECLARE @variavel_nome TipoDeDado;
```

### Detalhes
- O nome da variável deve começar com o caractere `@`.
- O tipo de dado pode ser qualquer tipo de dado suportado pelo banco de dados, como `INT`, `VARCHAR`, `DATETIME`, entre outros.
- Variáveis declaradas com `DECLARE` têm escopo local e existem apenas dentro do bloco onde foram definidas.

## Exemplos
### Exemplo 1: Declarando uma variável inteira
```sql
DECLARE @contador INT;
SET @contador = 10;
SELECT @contador AS Contador;
```

### Exemplo 2: Usando uma variável em um loop
```sql
DECLARE @i INT = 1;
WHILE @i <= 5
BEGIN
    PRINT 'Número: ' + CAST(@i AS VARCHAR);
    SET @i = @i + 1;
END;
```

### Exemplo 3: Declarando uma variável de texto
```sql
DECLARE @nome VARCHAR(50);
SET @nome = 'João';
SELECT @nome AS Nome;
```

## Explicação
Um erro comum ao usar `DECLARE` é tentar utilizar uma variável fora de seu escopo. Como as variáveis são locais ao bloco onde foram declaradas, elas não estarão disponíveis fora desse contexto. Além disso, é importante garantir que o tipo de dado da variável seja compatível com os valores que você pretende armazenar, pois isso pode gerar erros de conversão.

Outro ponto a ser observado é que ao declarar uma variável, ela não é inicializada automaticamente. Portanto, é boa prática sempre usar o comando `SET` ou `SELECT` para atribuir um valor a ela logo após a declaração.

## Resumo em uma Frase
O comando `DECLARE` em SQL é utilizado para criar variáveis temporárias que facilitam a manipulação de dados durante a execução de scripts e stored procedures.