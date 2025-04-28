<!--
Meta Description: # SQL INSERT: Der Befehl zum Hinzufügen von Daten in Datenbanken ## Synopsis Der SQL-Befehl `INSERT` wird verwendet, um neue Datensätze in Tabellen ei...
Meta Keywords: insert, der, die, sql, ist
-->

# SQL INSERT: Der Befehl zum Hinzufügen von Daten in Datenbanken

## Synopsis
Der SQL-Befehl `INSERT` wird verwendet, um neue Datensätze in Tabellen einer relationalen Datenbank hinzuzufügen. Er ermöglicht das Einfügen von einzelnen oder mehreren Zeilen und ist ein grundlegender Bestandteil der Datenmanipulation in SQL.

## Dokumentation
Der `INSERT`-Befehl ist essenziell für die Erstellung und Verwaltung von Datensätzen in Datenbanken. Er wird typischerweise in der Form `INSERT INTO <Tabellenname> (Spalte1, Spalte2, ...) VALUES (Wert1, Wert2, ...);` verwendet.

### Zweck
- **Daten hinzufügen:** Der Hauptzweck des `INSERT`-Befehls ist es, neue Daten in eine Tabelle einzufügen.
- **Mehrere Zeilen einfügen:** Es ist möglich, mehrere Datensätze in einem einzigen Befehl hinzuzufügen, was die Effizienz erhöht.

### Verwendung
- **Einzelnes Einfügen:** Um einen einzelnen Datensatz hinzuzufügen, gibt man den Tabellennamen sowie die Spalten und die entsprechenden Werte an.
- **Mehrfaches Einfügen:** Um mehrere Datensätze hinzuzufügen, können die Werte in einer einzigen `VALUES`-Klausel durch Kommas getrennt werden.

### Details
- **Werttypen:** Die Werte müssen den Datentypen der jeweiligen Spalten entsprechen.
- **Automatische Werte:** Bei Verwendung von `AUTO_INCREMENT`-Spalten ist es nicht notwendig, einen Wert für diese Spalte anzugeben.
- **NULL-Werte:** Wenn eine Spalte NULL-Werte zulässt, kann diese auch weggelassen werden, sofern die NULL nicht den Primärschlüssel oder andere Einschränkungen verletzt.

## Beispiele
### Beispiel 1: Einzelner Datensatz
```sql
INSERT INTO kunden (name, email) VALUES ('Max Mustermann', 'max@example.com');
```

### Beispiel 2: Mehrere Datensätze
```sql
INSERT INTO produkte (name, preis) VALUES 
('Produkt A', 19.99),
('Produkt B', 29.99),
('Produkt C', 39.99);
```

### Beispiel 3: Mit automatischer ID
```sql
INSERT INTO bestellungen (kunde_id, produkt_id, menge) VALUES 
(1, 2, 3);
```

## Erklärung
- **Datenintegrität:** Achten Sie darauf, dass die Datenintegrität gewahrt bleibt. Der `INSERT`-Befehl kann fehlschlagen, wenn er gegen Primärschlüssel- oder Unique-Einschränkungen verstößt.
- **Transaktionen:** Bei komplexen Einfügungen ist es empfehlenswert, Transaktionen zu verwenden, um sicherzustellen, dass alle Einfügungen erfolgreich sind oder im Fehlerfall zurückgerollt werden.
- **Fehlermeldungen:** Bei der Verwendung des `INSERT`-Befehls können spezifische Fehlermeldungen auftreten, die auf Probleme wie Datentypkonflikte oder Violationen von Einschränkungen hinweisen.

## Ein-Satz-Zusammenfassung
Der SQL-Befehl `INSERT` dient dazu, neue Datensätze in eine Tabelle einzufügen und ist ein entscheidender Bestandteil der Datenmanipulation in relationalen Datenbanken.