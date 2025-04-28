<!--
Meta Description: # Comando SQL UPDATE: Atualizando Dados em Tabelas ## Sinopse O comando SQL UPDATE é utilizado para modificar dados existentes em uma tabela no banco ...
Meta Keywords: update, where, dados, comando, que
-->

# Comando SQL UPDATE: Atualizando Dados em Tabelas

## Sinopse
O comando SQL UPDATE é utilizado para modificar dados existentes em uma tabela no banco de dados. Com ele, é possível alterar valores de uma ou mais colunas, permitindo a atualização eficiente e precisa das informações.

## Documentação
### Propósito
O comando UPDATE tem como principal objetivo modificar registros já existentes em uma tabela. Ele permite que os desenvolvedores e administradores de banco de dados realizem alterações em campos específicos de uma ou mais linhas com base em condições definidas.

### Uso
A sintaxe básica do comando UPDATE é a seguinte:

```sql
UPDATE nome_da_tabela
SET coluna1 = valor1, coluna2 = valor2, ...
WHERE condição;
```

- **nome_da_tabela**: o nome da tabela que contém os dados a serem atualizados.
- **SET**: palavra-chave que indica quais colunas e valores devem ser atualizados.
- **colunaX**: o nome da coluna que será alterada.
- **valorX**: o novo valor que será atribuído à coluna.
- **WHERE**: cláusula opcional que especifica quais registros devem ser atualizados. Se omitida, todos os registros da tabela serão atualizados.

### Detalhes
- É importante usar a cláusula WHERE para evitar a atualização de todos os registros, a menos que isso seja intencional.
- O comando pode afetar múltiplas linhas se a condição do WHERE corresponder a mais de um registro.
- É recomendado fazer um backup dos dados antes de executar um UPDATE, especialmente em produção, para evitar perda de informações.

## Exemplos

### Exemplo 1: Atualizando um único registro
```sql
UPDATE clientes
SET cidade = 'São Paulo'
WHERE id = 1;
```
Este comando atualiza a cidade do cliente com ID 1 para 'São Paulo'.

### Exemplo 2: Atualizando múltiplos registros
```sql
UPDATE produtos
SET preco = preco * 0.9
WHERE categoria = 'Eletrônicos';
```
Aqui, todos os produtos da categoria 'Eletrônicos' têm seus preços reduzidos em 10%.

### Exemplo 3: Atualizando sem a cláusula WHERE (cuidado!)
```sql
UPDATE funcionarios
SET salario = salario + 500;
```
Esse comando aumentará o salário de todos os funcionários em 500 unidades monetárias. Use com cautela!

## Explicação
- **Cuidado com a cláusula WHERE**: A omissão da cláusula WHERE resultará na atualização de todos os registros na tabela, o que pode não ser o comportamento desejado e causar perda de dados.
- **Transações**: Em ambientes onde a integridade dos dados é crucial, considere usar transações para reverter mudanças em caso de erro.
- **Desempenho**: Atualizações em tabelas grandes podem ser lentas; considere a indexação das colunas utilizadas na cláusula WHERE para melhorar o desempenho.

## Resumo em uma frase
O comando SQL UPDATE é essencial para modificar dados existentes em tabelas, permitindo atualizações precisas e controladas.