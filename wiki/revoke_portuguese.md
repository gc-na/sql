<!--
Meta Description: # REVOKE em SQL: Controle de Permissões de Acesso ## Sinopse O comando **REVOKE** em SQL é utilizado para remover permissões previamente concedidas a ...
Meta Keywords: revoke, permissões, que, dados, sql
-->

# REVOKE em SQL: Controle de Permissões de Acesso

## Sinopse
O comando **REVOKE** em SQL é utilizado para remover permissões previamente concedidas a usuários ou papéis, permitindo que os administradores de banco de dados mantenham um controle rigoroso sobre quem pode acessar ou manipular dados.

## Documentação
O comando **REVOKE** é parte fundamental da gestão de segurança de bancos de dados, permitindo que os administradores revoguem direitos de acesso. Ele pode ser utilizado em diversos sistemas de gerenciamento de banco de dados (SGBDs), como MySQL, PostgreSQL e SQL Server, com pequenas variações na sintaxe.

### Propósito
O propósito do **REVOKE** é garantir que, quando um usuário não deve mais ter acesso a determinadas funcionalidades ou dados, esse acesso possa ser removido de forma eficaz.

### Uso
A sintaxe básica do comando **REVOKE** é a seguinte:

```sql
REVOKE [tipo_de_permissão] ON [objeto] FROM [usuário];
```

- **tipo_de_permissão**: Especifica a permissão que está sendo revogada (por exemplo, SELECT, INSERT, UPDATE).
- **objeto**: O objeto do banco de dados do qual a permissão está sendo removida (como uma tabela ou vista).
- **usuário**: O nome do usuário ou papel que está perdendo a permissão.

### Detalhes
- O **REVOKE** pode ser aplicado a permissões específicas ou a todas as permissões em um objeto.
- O comando pode ser usado em conjunto com o **GRANT**, que é o comando que concede permissões.
- Dependendo do SGBD, pode haver variações na forma como as permissões são gerenciadas.

## Exemplos

### Exemplo 1: Revogando Permissão de Seleção
```sql
REVOKE SELECT ON tabela_exemplo FROM usuario_exemplo;
```
Neste exemplo, o usuário `usuario_exemplo` perde a permissão de selecionar dados da `tabela_exemplo`.

### Exemplo 2: Revogando Todas as Permissões
```sql
REVOKE ALL PRIVILEGES ON tabela_exemplo FROM usuario_exemplo;
```
Aqui, todas as permissões do `usuario_exemplo` sobre a `tabela_exemplo` são revogadas.

### Exemplo 3: Revogando Permissão de Inserção
```sql
REVOKE INSERT ON tabela_exemplo FROM grupo_exemplo;
```
Neste caso, o grupo `grupo_exemplo` perde a permissão para inserir dados na `tabela_exemplo`.

## Explicação
Um dos erros comuns ao usar o **REVOKE** é não especificar corretamente o tipo de permissão que se deseja remover. Além disso, é importante lembrar que, se o usuário ou grupo tiver permissões herdadas de um papel, a revogação deve ser feita no nível apropriado para garantir que o acesso seja completamente removido.

Outro ponto a ser observado é que, em alguns SGBDs, a revogação de permissões pode não ser imediata se houver dependências de outras permissões, o que pode causar confusões sobre a efetividade do comando.

## Resumo em Uma Linha
O comando **REVOKE** em SQL é utilizado para remover permissões de acesso a usuários ou papéis, garantindo a segurança e o controle sobre os dados do banco.