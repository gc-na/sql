<!--
Meta Description: # RENAME in SQL: Umbenennen von Tabellen und Spalten ## Synopsis Der SQL-Befehl `RENAME` wird verwendet, um den Namen von Datenbankobjekten, wie Tabel...
Meta Keywords: rename, sql, umbenennen, befehl, die
-->

# RENAME in SQL: Umbenennen von Tabellen und Spalten

## Synopsis
Der SQL-Befehl `RENAME` wird verwendet, um den Namen von Datenbankobjekten, wie Tabellen und Spalten, zu ändern. Dieser Befehl ist essenziell, um die Datenbankstruktur klarer und verständlicher zu gestalten.

## Dokumentation
Der `RENAME`-Befehl ist in verschiedenen SQL-Datenbanksystemen implementiert, einschließlich MySQL, PostgreSQL und Oracle. Der Hauptzweck dieses Befehls besteht darin, die Lesbarkeit und Wartbarkeit von Datenbanken zu verbessern.

### Verwendung
Die allgemeine Syntax für den `RENAME`-Befehl lautet:

#### Umbenennen einer Tabelle:
```sql
RENAME TABLE alter_tabellenname TO neuer_tabellenname;
```

#### Umbenennen einer Spalte:
In vielen SQL-Datenbanken wird das Umbenennen einer Spalte nicht direkt mit `RENAME` durchgeführt. Stattdessen wird häufig der `ALTER TABLE`-Befehl verwendet. Die Syntax sieht wie folgt aus:

```sql
ALTER TABLE tabellenname RENAME COLUMN alter_spaltenname TO neuer_spaltenname;
```

### Details
- **Berechtigungen**: Um Tabellen oder Spalten umzubenennen, benötigen Sie in der Regel die entsprechenden Berechtigungen für die betroffenen Objekte.
- **Referenzen**: Überprüfen Sie, ob es abhängige Objekte (wie Views oder Stored Procedures) gibt, die auf den alten Namen verweisen, da diese möglicherweise aktualisiert werden müssen.

## Beispiele
### Beispiel 1: Umbenennen einer Tabelle
```sql
RENAME TABLE kunden TO kunden_neu;
```

### Beispiel 2: Umbenennen einer Spalte
```sql
ALTER TABLE kunden RENAME COLUMN adresse TO wohnort;
```

## Erklärung
Ein häufiges Problem beim Umbenennen von Tabellen oder Spalten ist, dass bestehende Abfragen oder Anwendungen, die auf den alten Namen zugreifen, dadurch fehlschlagen können. Es ist ratsam, nach dem Umbenennen eine umfassende Prüfung durchzuführen, um sicherzustellen, dass alle Abhängigkeiten aktualisiert wurden.

Ein weiteres häufiges Missverständnis besteht darin, dass einige SQL-Datenbankmanagementsysteme (DBMS) den `RENAME`-Befehl nicht unterstützen oder ihn anders implementieren. Beispielsweise unterstützen nicht alle Systeme das Umbenennen von Spalten direkt mit dem `RENAME`-Befehl, weshalb der `ALTER TABLE`-Befehl häufig bevorzugt wird.

## Ein-Satz-Zusammenfassung
Der `RENAME`-Befehl in SQL ermöglicht es Benutzern, Tabellen und Spalten umzubenennen, um die Datenbankstruktur zu optimieren.