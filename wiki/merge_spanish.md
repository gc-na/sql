<!--
Meta Description: # MERGE en SQL: Comando para la Gestión Eficiente de Datos ## Sinopsis El comando **MERGE** en SQL se utiliza para realizar operaciones de combinación...
Meta Keywords: origen, destino, que, when, matched
-->

# MERGE en SQL: Comando para la Gestión Eficiente de Datos

## Sinopsis
El comando **MERGE** en SQL se utiliza para realizar operaciones de combinación (insertar, actualizar o eliminar) en una tabla destino basada en los registros de una tabla origen. Este comando es especialmente útil para mantener la integridad de los datos y optimizar el rendimiento en la manipulación de grandes conjuntos de datos.

## Documentación
### Propósito
El propósito del comando **MERGE** es simplificar la lógica de actualización de datos en una base de datos, permitiendo que una única instrucción combine múltiples operaciones en una sola acción. Esto es ideal para situaciones en las que se necesita sincronizar datos entre tablas.

### Uso
La sintaxis básica del comando **MERGE** es la siguiente:

```sql
MERGE INTO tabla_destino AS destino
USING tabla_origen AS origen
ON condición
WHEN MATCHED THEN
    acción_actualizar
WHEN NOT MATCHED BY TARGET THEN
    acción_insertar
WHEN NOT MATCHED BY SOURCE THEN
    acción_eliminar;
```

- **tabla_destino**: La tabla en la que se aplicarán las modificaciones.
- **tabla_origen**: La tabla que contiene los datos que se usarán para la comparación.
- **condición**: La lógica que determina cómo se emparejan los registros entre la tabla destino y la tabla origen.
- **acción_actualizar**: La operación que se realizará si hay coincidencia entre las tablas.
- **acción_insertar**: La operación que se realizará si no hay coincidencia en la tabla destino.
- **acción_eliminar**: La operación que se realizará si no hay coincidencia en la tabla origen.

### Detalles
- Este comando es soportado por varios sistemas de gestión de bases de datos como SQL Server, Oracle y PostgreSQL, aunque la sintaxis puede variar ligeramente.
- Es importante definir correctamente las condiciones para evitar resultados inesperados.
- El uso de **MERGE** puede mejorar el rendimiento al reducir la cantidad de operaciones necesarias para sincronizar datos.

## Ejemplos
### Ejemplo Básico
Supongamos que tenemos dos tablas: `clientes_destino` y `clientes_origen`. Queremos actualizar la tabla de destino con información de la tabla de origen.

```sql
MERGE INTO clientes_destino AS destino
USING clientes_origen AS origen
ON destino.id_cliente = origen.id_cliente
WHEN MATCHED THEN
    UPDATE SET destino.nombre = origen.nombre, destino.email = origen.email
WHEN NOT MATCHED BY TARGET THEN
    INSERT (id_cliente, nombre, email) VALUES (origen.id_cliente, origen.nombre, origen.email)
WHEN NOT MATCHED BY SOURCE THEN
    DELETE;
```

### Ejemplo con Condiciones
Podemos también agregar condiciones adicionales en las acciones:

```sql
MERGE INTO productos_destino AS destino
USING productos_origen AS origen
ON destino.id_producto = origen.id_producto
WHEN MATCHED AND origen.precio < destino.precio THEN
    UPDATE SET destino.precio = origen.precio
WHEN NOT MATCHED BY TARGET THEN
    INSERT (id_producto, nombre, precio) VALUES (origen.id_producto, origen.nombre, origen.precio);
```

## Explicación
### Errores Comunes
- **Condiciones Incorrectas**: Un error común es establecer condiciones que no reflejan adecuadamente la relación entre las tablas, lo que puede resultar en actualizaciones o eliminaciones no deseadas.
- **Falta de Índices**: La falta de índices en las columnas utilizadas en la condición puede llevar a un rendimiento deficiente en la ejecución del comando.
- **Confusión en las Acciones**: Es esencial entender la diferencia entre `WHEN MATCHED`, `WHEN NOT MATCHED BY TARGET` y `WHEN NOT MATCHED BY SOURCE`, ya que cada uno tiene un propósito específico.

## Resumen en Una Línea
El comando **MERGE** en SQL permite combinar operaciones de inserción, actualización y eliminación en una única instrucción para gestionar eficientemente los datos entre tablas.