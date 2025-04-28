<!--
Meta Description: # CREATE – Der SQL-Befehl zum Erstellen von Datenbankobjekten ## Synopsis Der SQL-Befehl `CREATE` wird verwendet, um neue Datenbankobjekte wie Tabelle...
Meta Keywords: create, die, sql, erstellen, der
-->

# CREATE – Der SQL-Befehl zum Erstellen von Datenbankobjekten

## Synopsis
Der SQL-Befehl `CREATE` wird verwendet, um neue Datenbankobjekte wie Tabellen, Sichten, Indizes und Datenbanken zu erstellen. Er ist ein grundlegender Bestandteil der Datenbankverwaltung und ermöglicht die Strukturierung von Daten.

## Documentation
Der `CREATE`-Befehl ist essenziell für die Definition der Datenstruktur in einer relationalen Datenbank. Mit diesem Befehl können verschiedene Objekte erstellt werden:

- **Tabellen**: Die grundlegenden Strukturen, in denen Daten gespeichert werden.
- **Sichten**: Virtuelle Tabellen, die auf Abfragen basieren und eine vereinfachte Datenansicht bieten.
- **Indizes**: Strukturen, die den Zugriff auf Daten in Tabellen beschleunigen.
- **Datenbanken**: Container für Tabellen und andere Objekte.

### Syntax
Die allgemeine Syntax für den `CREATE`-Befehl variiert je nach Objektart. Hier sind einige Beispiele:

#### Erstellen einer Tabelle
```sql
CREATE TABLE tabellenname (
    spalte1 datentyp [optionen],
    spalte2 datentyp [optionen],
    ...
);
```

#### Erstellen einer Sicht
```sql
CREATE VIEW sichtname AS
SELECT spalte1, spalte2
FROM tabellenname
WHERE bedingung;
```

#### Erstellen eines Index
```sql
CREATE INDEX indexname ON tabellenname (spalte);
```

### Verwendung
Der `CREATE`-Befehl wird in SQL-Datenbanksystemen wie MySQL, PostgreSQL, SQL Server und Oracle verwendet. Bei der Erstellung von Objekten sind spezifische Berechtigungen erforderlich, und die Syntax kann je nach Datenbankmanagementsystem (DBMS) leicht variieren.

## Examples
### Beispiel 1: Erstellen einer Tabelle
```sql
CREATE TABLE kunden (
    kunden_id INT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100) UNIQUE
);
```

### Beispiel 2: Erstellen einer Sicht
```sql
CREATE VIEW kunden_email AS
SELECT name, email
FROM kunden
WHERE email IS NOT NULL;
```

### Beispiel 3: Erstellen eines Index
```sql
CREATE INDEX idx_kunden_name ON kunden (name);
```

## Explanation
Ein häufiges Problem beim Erstellen von Objekten mit dem `CREATE`-Befehl ist die Verwendung von bereits existierenden Objektnamen. Wenn Sie versuchen, ein Objekt mit einem Namen zu erstellen, der bereits verwendet wird, wird ein Fehler ausgegeben. Um dies zu umgehen, können Sie den Befehl `CREATE OR REPLACE` verwenden, wenn dies von Ihrem DBMS unterstützt wird.

Ein weiterer Fall ist die Wahl des richtigen Datentyps. Falsche Datentypen können zu unerwarteten Ergebnissen führen und die Datenintegrität beeinträchtigen. Achten Sie darauf, alle Anforderungen an die Spalte wie `NOT NULL` oder `UNIQUE` korrekt zu setzen.

## One Line Summary
Der `CREATE`-Befehl in SQL dient zur Erstellung von Datenbankobjekten wie Tabellen, Sichten und Indizes, um die Datenstruktur zu definieren.