<!--
Meta Description: # END in SQL: Verwendung und Bedeutung ## Synopsis Das Schlüsselwort "END" in SQL wird verwendet, um das Ende von Blockstrukturen wie CASE-Anweisungen...
Meta Keywords: end, sql, case, und, von
-->

# END in SQL: Verwendung und Bedeutung

## Synopsis
Das Schlüsselwort "END" in SQL wird verwendet, um das Ende von Blockstrukturen wie CASE-Anweisungen und Schleifen zu kennzeichnen. Es spielt eine entscheidende Rolle in der Strukturierung und Logik von SQL-Abfragen.

## Documentation
### Zweck
Das "END"-Schlüsselwort wird hauptsächlich in Kombination mit Anweisungen verwendet, die mehrere Bedingungen oder Anweisungen enthalten. Es signalisiert das Ende eines bestimmten Blocks und ist erforderlich, um die Lesbarkeit und Struktur der SQL-Abfragen zu gewährleisten.

### Verwendung
In SQL wird "END" häufig in den folgenden Kontexten verwendet:

1. **CASE-Anweisung**: In einer CASE-Anweisung wird "END" verwendet, um das Ende der Bedingungen zu kennzeichnen.
2. **BEGIN...END-Blöcke**: In gespeicherten Prozeduren oder Funktionen wird "END" verwendet, um den Abschluss von Codeblöcken zu definieren.

#### Syntax
Die allgemeine Syntax für die Verwendung von "END" in einer CASE-Anweisung sieht wie folgt aus:

```sql
CASE
    WHEN Bedingung1 THEN Ergebnis1
    WHEN Bedingung2 THEN Ergebnis2
    ELSE ErgebnisStandard
END
```

Für BEGIN...END-Blöcke könnte die Syntax so aussehen:

```sql
BEGIN
    -- SQL Anweisungen
END
```

## Examples
### Beispiel 1: Verwendung von CASE mit END
```sql
SELECT 
    Name, 
    CASE 
        WHEN Punktzahl >= 90 THEN 'A' 
        WHEN Punktzahl >= 80 THEN 'B'
        WHEN Punktzahl >= 70 THEN 'C'
        ELSE 'D'
    END AS Note
FROM Studenten;
```

### Beispiel 2: BEGIN...END Block
```sql
CREATE PROCEDURE BeispielProzedur AS
BEGIN
    -- Anweisungen der Prozedur
    INSERT INTO Tabelle (Spalte1, Spalte2) VALUES (Wert1, Wert2);
END;
```

## Explanation
Ein häufiges Problem bei der Verwendung von "END" ist das Vergessen, es am Ende eines Blocks oder einer CASE-Anweisung zu setzen. Dies führt zu Syntaxfehlern oder unerwartetem Verhalten in der SQL-Abfrage. Es ist wichtig, sicherzustellen, dass jede CASE-Anweisung und jeder BEGIN-Block ordnungsgemäß mit "END" abgeschlossen wird.

Zusätzlich sollten Benutzer darauf achten, die richtige Anzahl von "WHEN"-Bedingungen in einer CASE-Anweisung zu verwenden, um logische Fehler zu vermeiden. Ein gut strukturierter SQL-Code verbessert nicht nur die Lesbarkeit, sondern minimiert auch Fehler und Missverständnisse.

## One Line Summary
Das "END"-Schlüsselwort in SQL markiert das Ende von CASE-Anweisungen und Blockstrukturen und ist entscheidend für die korrekte Ausführung von SQL-Abfragen.