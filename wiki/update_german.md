<!--
Meta Description: # UPDATE in SQL: So aktualisieren Sie Datensätze effizient ## Synopsis Der SQL-Befehl `UPDATE` ermöglicht es Benutzern, bestehende Datensätze in einer...
Meta Keywords: der, update, die, werden, sql
-->

# UPDATE in SQL: So aktualisieren Sie Datensätze effizient

## Synopsis
Der SQL-Befehl `UPDATE` ermöglicht es Benutzern, bestehende Datensätze in einer Datenbanktabelle zu ändern. Mit dieser Anweisung können Sie spezifische Felder in einem oder mehreren Datensätzen aktualisieren, basierend auf definierten Bedingungen.

## Dokumentation
Der `UPDATE`-Befehl wird verwendet, um die Werte in einer oder mehreren Spalten einer Tabelle zu ändern. Die grundlegende Syntax lautet:

```sql
UPDATE tabellenname
SET spalte1 = wert1, spalte2 = wert2, ...
WHERE bedingung;
```

### Zweck
Der Hauptzweck des `UPDATE`-Befehls ist es, Daten in einer Tabelle zu aktualisieren, ohne die gesamte Tabelle neu zu schreiben oder zu löschen. Dies ist besonders nützlich, wenn nur bestimmte Informationen geändert werden müssen.

### Verwendung
- **tabellenname**: Der Name der Tabelle, die aktualisiert werden soll.
- **spalte1, spalte2, ...**: Die Spalten, deren Werte aktualisiert werden.
- **wert1, wert2, ...**: Die neuen Werte, die den entsprechenden Spalten zugewiesen werden.
- **WHERE bedingung**: Eine optionale Klausel, die bestimmt, welche Datensätze aktualisiert werden. Ohne diese Klausel werden alle Datensätze in der Tabelle aktualisiert, was oft zu unerwünschten Ergebnissen führen kann.

## Beispiele
### Beispiel 1: Einfaches Update
```sql
UPDATE kunden
SET nachname = 'Müller'
WHERE kunden_id = 1;
```
In diesem Beispiel wird der Nachname des Kunden mit der ID 1 auf "Müller" geändert.

### Beispiel 2: Mehrere Spalten aktualisieren
```sql
UPDATE produkte
SET preis = preis * 1.1, lagerbestand = lagerbestand - 1
WHERE kategorie = 'Elektronik';
```
Hier werden alle Produkte in der Kategorie "Elektronik" um 10% im Preis erhöht und der Lagerbestand um 1 verringert.

### Beispiel 3: Update ohne WHERE
```sql
UPDATE benutzer
SET status = 'aktiv';
```
In diesem Beispiel wird der Status aller Benutzer auf "aktiv" gesetzt. Dies ist ein gefährlicher Befehl, da er alle Datensätze betrifft.

## Erklärung
Ein häufiges Problem beim Arbeiten mit dem `UPDATE`-Befehl ist das Fehlen der `WHERE`-Klausel. Wenn diese Klausel nicht angegeben wird, werden alle Datensätze in der Tabelle aktualisiert, was zu unerwarteten Ergebnissen führen kann. Ein weiteres häufiges Missverständnis ist, dass der `UPDATE`-Befehl keine Rückgängig-Funktion hat; daher sollte immer eine Sicherung der Datenbank vor dem Ausführen von Updates gemacht werden.

Zusätzlich kann es notwendig sein, Transaktionen zu verwenden, um sicherzustellen, dass mehrere aufeinanderfolgende `UPDATE`-Befehle entweder vollständig erfolgreich oder vollständig fehlgeschlagen sind. Dies kann mit dem `BEGIN TRANSACTION`, `COMMIT` und `ROLLBACK`-Befehlen erreicht werden.

## Ein-Satz-Zusammenfassung
Der `UPDATE`-Befehl in SQL ermöglicht es, spezifische Datensätze in einer Tabelle effizient zu ändern, wobei die Verwendung der WHERE-Klausel entscheidend für die Vermeidung unerwünschter Aktualisierungen ist.