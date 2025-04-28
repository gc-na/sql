<!--
Meta Description: # Actualización en SQL: El Comando UPDATE ## Sinopsis El comando SQL `UPDATE` se utiliza para modificar registros existentes en una tabla de base de d...
Meta Keywords: los, update, datos, registros, que
-->

# Actualización en SQL: El Comando UPDATE

## Sinopsis
El comando SQL `UPDATE` se utiliza para modificar registros existentes en una tabla de base de datos. Permite cambiar uno o varios campos de uno o más registros, facilitando la gestión de datos en sistemas de información.

## Documentación
### Propósito
El propósito del comando `UPDATE` es actualizar los valores de las columnas en las filas que cumplen con una condición específica. Esto es fundamental para mantener la integridad y la relevancia de los datos dentro de una base de datos.

### Uso
La sintaxis básica del comando `UPDATE` es la siguiente:

```sql
UPDATE nombre_tabla
SET columna1 = valor1, columna2 = valor2, ...
WHERE condición;
```

- **nombre_tabla**: Especifica la tabla en la que se desea realizar la actualización.
- **SET**: Indica las columnas que se van a modificar junto con los nuevos valores.
- **WHERE**: Esta cláusula es crucial, ya que determina qué registros serán actualizados. Si se omite, se actualizarán todos los registros de la tabla.

### Detalles
- Se pueden actualizar múltiples columnas al mismo tiempo separando cada asignación con comas.
- Es recomendable siempre usar la cláusula `WHERE` para evitar actualizar todos los registros por error.
- Los tipos de datos deben coincidir con los definidos en la tabla, de lo contrario se generarán errores.

## Ejemplos
### Ejemplo 1: Actualizar un único campo
```sql
UPDATE empleados
SET salario = 50000
WHERE id_empleado = 1;
```
Este ejemplo actualiza el salario del empleado con ID 1 a 50000.

### Ejemplo 2: Actualizar múltiples campos
```sql
UPDATE productos
SET precio = 20.99, stock = 50
WHERE id_producto = 10;
```
Aquí se actualizan el precio y el stock del producto con ID 10.

### Ejemplo 3: Actualizar múltiples registros
```sql
UPDATE clientes
SET estado = 'Inactivo'
WHERE ultimo_pedido < '2023-01-01';
```
Este comando establece el estado de todos los clientes que no han realizado pedidos desde antes del 1 de enero de 2023 a 'Inactivo'.

## Explicación
### Errores Comunes
- **Omitir la cláusula WHERE**: Esto puede resultar en la actualización de todos los registros de la tabla, lo que generalmente no es deseado.
- **Usar valores incorrectos**: Asegúrese de que los valores asignados a las columnas sean del tipo adecuado.
- **No hacer un respaldo previo**: Antes de realizar actualizaciones masivas, es prudente respaldar los datos.

### Notas Adicionales
- Es posible utilizar transacciones para agrupar múltiples comandos `UPDATE` y asegurar que se ejecuten de manera atómica.
- Algunas bases de datos permiten el uso de subconsultas en el `SET` para establecer nuevos valores basados en otros datos.

## Resumen en una línea
El comando `UPDATE` en SQL se utiliza para modificar uno o más registros en una tabla, permitiendo mantener actualizados los datos en una base de datos.