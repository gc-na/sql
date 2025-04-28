<!--
Meta Description: # INSERT en SQL: Cómo Agregar Datos a una Base de Datos ## Sinopsis El comando `INSERT` en SQL se utiliza para agregar nuevas filas de datos a una tab...
Meta Keywords: datos, insert, una, los, sql
-->

# INSERT en SQL: Cómo Agregar Datos a una Base de Datos

## Sinopsis
El comando `INSERT` en SQL se utiliza para agregar nuevas filas de datos a una tabla en una base de datos. Es una de las operaciones más fundamentales en la manipulación de datos, permitiendo a los usuarios introducir información en sus sistemas de gestión de bases de datos.

## Documentación
El comando `INSERT` permite añadir uno o más registros en una tabla. Su uso correcto es esencial para mantener la integridad y la coherencia de los datos almacenados.

### Estructura del Comando
La sintaxis básica para el comando `INSERT` es la siguiente:

```sql
INSERT INTO nombre_tabla (columna1, columna2, columna3, ...)
VALUES (valor1, valor2, valor3, ...);
```

### Componentes:
- **nombre_tabla**: Especifica la tabla donde se insertarán los datos.
- **columna1, columna2, ...**: Son los nombres de las columnas en las que se insertarán los valores.
- **valor1, valor2, ...**: Son los valores que se insertarán en las columnas correspondientes.

### Inserción Múltiple
También se pueden insertar múltiples filas en una sola instrucción:

```sql
INSERT INTO nombre_tabla (columna1, columna2)
VALUES (valor1a, valor2a),
       (valor1b, valor2b),
       (valor1c, valor2c);
```

## Ejemplos
### Ejemplo Básico
Supongamos que tenemos una tabla llamada `clientes` con las columnas `nombre`, `apellido` y `correo`.

```sql
INSERT INTO clientes (nombre, apellido, correo)
VALUES ('Juan', 'Pérez', 'juan.perez@example.com');
```

### Inserción Múltiple
Para insertar varios registros al mismo tiempo:

```sql
INSERT INTO clientes (nombre, apellido, correo)
VALUES ('Ana', 'García', 'ana.garcia@example.com'),
       ('Luis', 'Martínez', 'luis.martinez@example.com');
```

## Explicación
Al utilizar el comando `INSERT`, es importante tener en cuenta algunos aspectos:

1. **Restricciones de la Tabla**: Asegúrate de que los datos que intentas insertar no violen ninguna restricción, como claves primarias o restricciones de unicidad.
2. **Tipos de Datos**: Los valores que se insertan deben coincidir con los tipos de datos definidos en la tabla. Por ejemplo, intentar insertar un texto en una columna de tipo numérico generará un error.
3. **Valores Nulos**: Si alguna columna permite valores nulos y no se especifica un valor para esa columna en la instrucción `INSERT`, se insertará automáticamente un valor nulo.

### Errores Comunes
- **Violación de Clave Primaria**: Intentar insertar un registro con un valor que ya existe en una columna definida como clave primaria resultará en un error.
- **Faltan Valores**: Si no se especifican todos los valores requeridos y la columna no permite nulos, también se producirá un error.

## Resumen en una Línea
El comando `INSERT` en SQL permite agregar nuevas filas de datos a una tabla, siendo fundamental para la gestión de bases de datos.