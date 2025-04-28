<!--
Meta Description: # SET in SQL: Ein umfassender Leitfaden ## Zusammenfassung Der SQL-Befehl "SET" wird verwendet, um Variablen zu initialisieren und Werte in SQL-Datenb...
Meta Keywords: set, sql, die, session, wird
-->

# SET in SQL: Ein umfassender Leitfaden

## Zusammenfassung
Der SQL-Befehl "SET" wird verwendet, um Variablen zu initialisieren und Werte in SQL-Datenbanken festzulegen, sowohl in Transaktionen als auch in Abfragen.

## Dokumentation
Der Befehl "SET" in SQL hat mehrere Anwendungen, die sich je nach Kontext unterscheiden. Primär wird "SET" verwendet, um:

1. **Variablen zu definieren**: In SQL kann man mit "SET" eine Variable initialisieren und ihr einen bestimmten Wert zuweisen. Dies ist besonders nützlich in Stored Procedures und Funktionen.
  
2. **Einstellungen zu ändern**: Mit "SET" können spezifische Einstellungen der SQL-Session geändert werden, wie etwa das Setzen des Autocommit-Status oder das Anpassen von Zeitüberschreitungen.

### Verwendung
Die grundlegende Syntax für die Verwendung von "SET" ist wie folgt:

```sql
SET variable_name = value;
```

Für die Änderung von Session-Einstellungen kann die Syntax wie folgt aussehen:

```sql
SET GLOBAL variable_name = value; -- für globale Einstellungen
SET SESSION variable_name = value; -- für session-spezifische Einstellungen
```

## Beispiele

### Beispiel 1: Variable setzen
```sql
DECLARE @myVar INT;
SET @myVar = 10;
SELECT @myVar AS 'Wert';
```

### Beispiel 2: Session-Einstellung ändern
```sql
SET SESSION sql_mode = 'STRICT_TRANS_TABLES';
```

### Beispiel 3: Autocommit deaktivieren
```sql
SET autocommit = 0;
```

## Erklärung
- **Häufige Fallstricke**: Ein häufiges Missverständnis ist, dass "SET" in SQL nicht mit dem SQL-Befehl "UPDATE" verwechselt werden sollte. Während "SET" verwendet wird, um Werte zuzuweisen, wird "UPDATE" verwendet, um bereits vorhandene Daten in einer Tabelle zu ändern.
  
- **Variablenbereich**: Beachten Sie, dass Variablen, die mit "SET" deklariert werden, nur innerhalb des aktuellen Geltungsbereichs (z.B. einer Stored Procedure oder einer Sitzung) verfügbar sind.

- **Einstellungseffekte**: Änderungen, die mit "SET" an Session-Variablen vorgenommen werden, gelten nur für die aktuelle Sitzung und gehen verloren, wenn die Sitzung beendet wird.

## Zusammenfassung in einem Satz
Der SQL-Befehl "SET" wird verwendet, um Variablen zu initialisieren und Session-Einstellungen in SQL-Datenbanken festzulegen.