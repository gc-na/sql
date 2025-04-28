<!--
Meta Description: # SELECT: Der Schlüsselbefehl zur Datenabfrage in SQL ## Synopsis Der SQL-Befehl `SELECT` ist das grundlegendste und am häufigsten verwendete Werkzeug...
Meta Keywords: die, der, select, sql, kunden
-->

# SELECT: Der Schlüsselbefehl zur Datenabfrage in SQL

## Synopsis
Der SQL-Befehl `SELECT` ist das grundlegendste und am häufigsten verwendete Werkzeug zur Abfrage von Daten aus einer Datenbank. Er ermöglicht es Benutzern, spezifische Daten aus einer oder mehreren Tabellen abzurufen und bietet zahlreiche Optionen zur Anpassung der Abfrageergebnisse.

## Dokumentation
### Zweck
Der `SELECT`-Befehl wird verwendet, um Daten aus einer oder mehreren Tabellen in einer relationalen Datenbank abzurufen. Er ermöglicht es Benutzern, gezielt Informationen zu extrahieren, die für Analysen, Berichte oder Datenverarbeitung benötigt werden.

### Verwendung
Die grundlegende Syntax für den `SELECT`-Befehl lautet:

```sql
SELECT [Spaltenname1], [Spaltenname2], ...
FROM [Tabellenname]
WHERE [Bedingung];
```

- **SELECT**: Gibt die Spalten an, die zurückgegeben werden sollen. Das Platzhalterzeichen `*` kann verwendet werden, um alle Spalten auszuwählen.
- **FROM**: Gibt die Tabelle an, aus der die Daten abgerufen werden.
- **WHERE**: (optional) Legt Bedingungen fest, welche Datensätze zurückgegeben werden sollen.

### Details
- **DISTINCT**: Mit dem Schlüsselwort `DISTINCT` können doppelte Werte in den Ergebnissen entfernt werden.
- **ORDER BY**: Mit diesem Befehl können die Ergebnisse sortiert werden.
- **GROUP BY**: Ermöglicht die Gruppierung von Datensätzen basierend auf den Werten einer oder mehrerer Spalten.
- **JOIN**: Ermöglicht das Kombinieren von Daten aus mehreren Tabellen.

## Beispiele
### Einfaches Beispiel
Um alle Spalten aus der Tabelle `Kunden` abzurufen:

```sql
SELECT * FROM Kunden;
```

### Abfrage mit spezifischen Spalten
Um nur die Spalten `Vorname` und `Nachname` aus der Tabelle `Kunden` abzurufen:

```sql
SELECT Vorname, Nachname FROM Kunden;
```

### Abfrage mit WHERE-Klausel
Um nur die Kunden zu sehen, die in der Stadt "Berlin" wohnen:

```sql
SELECT * FROM Kunden WHERE Stadt = 'Berlin';
```

### Verwendung von DISTINCT
Um nur einzigartige Städte aus der Tabelle `Kunden` abzurufen:

```sql
SELECT DISTINCT Stadt FROM Kunden;
```

### Daten sortieren
Um die Kunden nach Nachnamen aufsteigend zu sortieren:

```sql
SELECT * FROM Kunden ORDER BY Nachname ASC;
```

## Erklärung
Ein häufiges Problem bei der Verwendung des `SELECT`-Befehls ist die falsche Anwendung der `WHERE`-Klausel, die zu unerwarteten Ergebnissen führen kann. Achten Sie darauf, dass die Bedingungen korrekt formuliert sind. Ein weiterer häufiger Fehler ist das Vergessen des Semikolons am Ende der SQL-Anweisung, was zu Syntaxfehlern führen kann.

Zusätzlich sollten Benutzer bei der Verwendung von `JOIN` darauf achten, dass die richtigen Bedingungen zur Verknüpfung der Tabellen angegeben sind, um Datenintegrität zu gewährleisten und unerwartete Ergebnisse zu vermeiden.

## Ein-Satz-Zusammenfassung
Der `SELECT`-Befehl in SQL ist ein leistungsstarkes Werkzeug zum Abrufen von Daten aus einer Datenbank, das eine Vielzahl von Anpassungs- und Filtermöglichkeiten bietet.