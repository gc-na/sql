<!--
Meta Description: # END en SQL: Uso y Significado ## Sinopsis El comando `END` en SQL es utilizado para finalizar bloques de código en procedimientos almacenados, funci...
Meta Keywords: end, sql, uso, código, para
-->

# END en SQL: Uso y Significado

## Sinopsis
El comando `END` en SQL es utilizado para finalizar bloques de código en procedimientos almacenados, funciones, y control de flujo, como condicionales y bucles. Su correcta implementación es esencial para la legibilidad y la correcta ejecución de scripts SQL.

## Documentación
El `END` se utiliza principalmente en contextos donde se requiere cerrar un bloque de código. Esto incluye, pero no se limita a:

1. **Estructuras de Control**: En sentencias `IF`, `CASE`, y bucles como `WHILE`, `END` marca el punto final del bloque que se ejecuta bajo ciertas condiciones.
   
2. **Procedimientos Almacenados y Funciones**: En la definición de procedimientos o funciones, `END` indica el cierre de la definición de dicho objeto.

### Uso
La sintaxis general para usar `END` depende del contexto, pero comúnmente se utiliza de la siguiente manera:

```sql
IF condición THEN
    -- Código a ejecutar si la condición es verdadera
END IF;
```

En un procedimiento almacenado, podría verse así:

```sql
CREATE PROCEDURE nombre_procedimiento
AS
BEGIN
    -- Código del procedimiento
END;
```

## Ejemplos
### Ejemplo 1: Uso de `END` en un bloque IF
```sql
DECLARE @valor INT = 10;

IF @valor > 5
BEGIN
    PRINT 'El valor es mayor que 5';
END
```

### Ejemplo 2: Uso de `END` en un procedimiento almacenado
```sql
CREATE PROCEDURE Saludar
AS
BEGIN
    PRINT 'Hola, mundo!';
END;
```

### Ejemplo 3: Uso de `END` en un bucle WHILE
```sql
DECLARE @contador INT = 1;

WHILE @contador <= 5
BEGIN
    PRINT @contador;
    SET @contador = @contador + 1;
END
```

## Explicación
Al usar `END`, es fundamental recordar que este comando cierra el bloque de código anterior y debe ser utilizado correctamente para evitar errores de sintaxis. Algunas consideraciones importantes incluyen:

- **Bloques mal cerrados**: Si se omite `END`, el servidor SQL generará un error de sintaxis.
- **Indentación y legibilidad**: Mantener una buena indentación ayuda a identificar fácilmente los bloques de código, lo que es crucial en scripts SQL más extensos.
- **Uso en distintos contextos**: Asegúrate de usar `END` en el contexto correcto, ya que su uso varía entre procedimientos, funciones y estructuras de control.

## Resumen en una línea
El comando `END` en SQL es esencial para finalizar bloques de código en estructuras de control y definiciones de procedimientos o funciones, garantizando la correcta ejecución del script.