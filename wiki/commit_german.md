<!--
Meta Description: # COMMIT in SQL: So sichern Sie Transaktionen dauerhaft ## Synopsis Der SQL-Befehl "COMMIT" wird verwendet, um alle Änderungen, die innerhalb einer Tr...
Meta Keywords: commit, der, änderungen, alle, einer
-->

# COMMIT in SQL: So sichern Sie Transaktionen dauerhaft

## Synopsis
Der SQL-Befehl "COMMIT" wird verwendet, um alle Änderungen, die innerhalb einer Transaktion vorgenommen wurden, dauerhaft in der Datenbank zu speichern. Er spielt eine entscheidende Rolle bei der Gewährleistung der Datenintegrität und -konsistenz.

## Dokumentation
### Zweck
"COMMIT" ist ein SQL-Befehl, der das Ende einer Transaktion markiert und alle zuvor durchgeführten Änderungen in der Datenbank speichert. Es wird in Umgebungen verwendet, in denen mehrere Datenänderungen in einem einzigen Schritt durchgeführt werden, um sicherzustellen, dass entweder alle Änderungen erfolgreich angewendet werden oder keine.

### Verwendung
Der Befehl wird typischerweise nach einer Reihe von DML-Anweisungen (Data Manipulation Language) wie INSERT, UPDATE oder DELETE ausgeführt. Eine Transaktion beginnt normalerweise mit dem Befehl "BEGIN" oder "START TRANSACTION".

### Details
- **Syntax**:  
  ```sql
  COMMIT;
  ```
- **Transaktionskontrolle**: "COMMIT" wird häufig in Verbindung mit "ROLLBACK" verwendet. Während "COMMIT" alle Änderungen speichert, verwirft "ROLLBACK" alle Änderungen und stellt den vorherigen Zustand der Datenbank wieder her.
- **Datenbankverbindungen**: "COMMIT" wirkt sich nur auf die aktuelle Verbindung zur Datenbank aus. Änderungen sind erst nach dem Abschluss einer Transaktion über "COMMIT" sichtbar für andere Benutzer.

## Beispiele
### Beispiel 1: Grundlegende Verwendung von COMMIT
```sql
BEGIN;
INSERT INTO Kunden (Name, Stadt) VALUES ('Max Mustermann', 'Berlin');
UPDATE Bestellungen SET Status = 'Versendet' WHERE BestellID = 101;
COMMIT;
```
In diesem Beispiel werden ein neuer Kunde hinzugefügt und der Status einer Bestellung aktualisiert. Beide Änderungen werden durch den Befehl "COMMIT" dauerhaft gemacht.

### Beispiel 2: COMMIT nach mehreren Änderungen
```sql
BEGIN;
DELETE FROM Produkte WHERE Lagerbestand = 0;
INSERT INTO Protokoll (Aktion, Zeitstempel) VALUES ('Bestände gelöscht', NOW());
COMMIT;
```
Hier werden alle Produkte mit einem Lagerbestand von 0 gelöscht und eine Protokollzeile hinzugefügt, bevor die Änderungen mit "COMMIT" gespeichert werden.

## Erklärung
### Häufige Fallstricke
- **Vergessen von COMMIT**: Wenn "COMMIT" nicht ausgeführt wird und die Verbindung zur Datenbank abbricht, gehen alle ungespeicherten Änderungen verloren.
- **Transaktionsgrenzen**: Ein "COMMIT" kann nur innerhalb einer Transaktion verwendet werden. Das bedeutet, dass Sie sicherstellen müssen, dass die Transaktion korrekt begonnen wurde.
- **Isolationsebenen**: Unterschiedliche Isolationsebenen können das Verhalten von "COMMIT" beeinflussen, insbesondere in einer Umgebung mit mehreren Benutzern. Achten Sie darauf, dass konkurrierende Transaktionen korrekt verwaltet werden.

## Zusammenfassung in einem Satz
Der SQL-Befehl "COMMIT" speichert alle Änderungen einer Transaktion dauerhaft in der Datenbank und sichert so die Datenintegrität.