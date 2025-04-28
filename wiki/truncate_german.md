<!--
Meta Description: # TRUNCATE: SQL-Befehl zum schnellen Löschen von Daten in Tabellen ## Synopsis Der SQL-Befehl `TRUNCATE` wird verwendet, um alle Zeilen aus einer Tabe...
Meta Keywords: truncate, befehl, die, der, tabelle
-->

# TRUNCATE: SQL-Befehl zum schnellen Löschen von Daten in Tabellen

## Synopsis
Der SQL-Befehl `TRUNCATE` wird verwendet, um alle Zeilen aus einer Tabelle zu entfernen, ohne die Struktur der Tabelle selbst zu löschen. Dies geschieht in der Regel schneller und effizienter als das Löschen von Daten mit dem `DELETE`-Befehl.

## Documentation
### Zweck
Der `TRUNCATE`-Befehl ist ein DDL-Befehl (Data Definition Language), der dazu dient, alle Datensätze in einer Tabelle zu löschen. Anders als beim `DELETE`-Befehl wird bei `TRUNCATE` nicht jede Zeile einzeln gelöscht, was zu einer erheblichen Leistungsverbesserung führt, insbesondere bei großen Datensätzen.

### Verwendung
Die grundlegende Syntax von `TRUNCATE` sieht folgendermaßen aus:

```sql
TRUNCATE TABLE tabellenname;
```

### Details
- **Schnelligkeit**: `TRUNCATE` ist schneller als `DELETE`, da es keine Transaktionsprotokollierung für jede Zeile durchführt. Stattdessen wird die gesamte Tabelle als gelöscht markiert.
- **Kein WHERE**: Im Gegensatz zu `DELETE` unterstützt `TRUNCATE` keine `WHERE`-Klausel. Alle Datensätze werden ohne Ausnahme entfernt.
- **Kein Trigger**: `TRUNCATE` aktiviert keine Trigger, die auf Löschvorgänge reagieren könnten.
- **Rückgängig machen**: `TRUNCATE` kann in Transaktionen verwendet werden, aber es ist nicht möglich, einzelne Zeilen wiederherzustellen, nachdem der Befehl ausgeführt wurde.
- **Referenzielle Integrität**: Wenn die Tabelle, die Sie truncaten möchten, von anderen Tabellen referenziert wird (z.B. durch Fremdschlüssel), kann der Befehl nicht ausgeführt werden.

## Examples
### Beispiel 1: Einfaches Truncaten
```sql
TRUNCATE TABLE kunden;
```
Dieser Befehl entfernt alle Datensätze aus der Tabelle `kunden`.

### Beispiel 2: Truncaten in einer Transaktion
```sql
BEGIN TRANSACTION;
TRUNCATE TABLE bestellungen;
COMMIT;
```
Hier wird die Tabelle `bestellungen` innerhalb einer Transaktion truncatet, was bedeutet, dass der Befehl rückgängig gemacht werden kann, solange die Transaktion nicht abgeschlossen ist.

## Explanation
- **Gemeinsame Fallstricke**: Ein häufiger Fehler ist zu glauben, dass `TRUNCATE` rekursiv wirkt. Wenn die Ziel-Tabelle von anderen Tabellen referenziert wird, kann der Befehl nicht ausgeführt werden. Achten Sie auch darauf, dass alle abhängigen Tabellen, die durch Fremdschlüsselbeziehungen verbunden sind, vor dem Truncaten angepasst werden müssen.
- **Datenverlust**: Da `TRUNCATE` alle Daten unwiderruflich entfernt, sollten Sie sicherstellen, dass die Daten gesichert sind oder dass das Truncaten tatsächlich erforderlich ist.

## One Line Summary
`TRUNCATE` ist ein schneller SQL-Befehl, um alle Datensätze einer Tabelle zu entfernen, ohne deren Struktur zu löschen.