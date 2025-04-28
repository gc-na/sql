<!--
Meta Description: # SQL DECLARE: Variablen in SQL Abfragen deklarieren ## Synopsis Der `DECLARE` Befehl in SQL ermöglicht es Benutzern, Variablen zu definieren, die in ...
Meta Keywords: der, die, variablen, sql, und
-->

# SQL DECLARE: Variablen in SQL Abfragen deklarieren

## Synopsis
Der `DECLARE` Befehl in SQL ermöglicht es Benutzern, Variablen zu definieren, die in SQL-Abfragen oder Prozeduren verwendet werden können. Dies ist besonders nützlich für die Speicherung temporärer Daten und die Verbesserung der Lesbarkeit und Wartbarkeit von Code.

## Dokumentation
Der `DECLARE` Befehl wird in SQL verwendet, um Variablen zu erstellen, die in der aktuellen Sitzung oder innerhalb einer gespeicherten Prozedur verwendet werden können. Diese Variablen können verschiedene Datentypen annehmen, wie z.B. INTEGER, VARCHAR, DATETIME und viele andere.

### Zweck
- **Speicherung von Werten**: Variablen ermöglichen die temporäre Speicherung von Werten, die später in Abfragen oder Berechnungen verwendet werden können.
- **Verbesserung der Lesbarkeit**: Durch die Verwendung von Variablen wird der Code klarer und verständlicher.
- **Flexibilität in Abfragen**: Variablen können in verschiedenen Kontexten innerhalb einer Sitzung oder Prozedur eingesetzt werden.

### Nutzung
Um eine Variable zu deklarieren, wird der folgende Syntax verwendet:
```sql
DECLARE @VariableName Datentyp;
```
Hierbei ist `@VariableName` der Name der Variablen und `Datentyp` der Typ der Daten, die die Variable speichern kann.

## Beispiele
### Beispiel 1: Einfache Variable deklarieren
```sql
DECLARE @Alter INT;
SET @Alter = 30;
SELECT @Alter AS MeinAlter;
```
In diesem Beispiel wird eine INTEGER-Variable namens `@Alter` erstellt und auf den Wert 30 gesetzt. Anschließend wird der Wert der Variablen abgerufen.

### Beispiel 2: Verwendung in einer Prozedur
```sql
CREATE PROCEDURE BeispielProzedur
AS
BEGIN
    DECLARE @Summe INT;
    SET @Summe = 0;

    SELECT @Summe = SUM(Betrag) FROM Transaktionen;
    SELECT @Summe AS Gesamtsumme;
END;
```
Hier wird eine gespeicherte Prozedur erstellt, die die Summe aller Beträge aus der Tabelle `Transaktionen` berechnet und in der Variablen `@Summe` speichert.

## Erklärung
Ein häufiger Fehler beim Arbeiten mit `DECLARE` ist, die Datentypen nicht korrekt auszuwählen. Dies kann zu Laufzeitfehlern führen. Es ist wichtig, sicherzustellen, dass der Datentyp der Variablen mit dem erwarteten Wert übereinstimmt, um Typkonflikte zu vermeiden. 

Zusätzlich darf eine Variable nicht ohne vorherige Deklaration verwendet werden. Der Versuch, auf eine nicht deklarierte Variable zuzugreifen, führt zu einem Fehler.

## Ein-Satz-Zusammenfassung
Der `DECLARE` Befehl in SQL ermöglicht die Definition von Variablen zur temporären Speicherung von Daten innerhalb von Abfragen und Prozeduren, was die Flexibilität und Lesbarkeit des Codes erhöht.