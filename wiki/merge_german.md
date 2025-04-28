<!--
Meta Description: # MERGE in SQL: Ein umfassender Leitfaden für Datenbankupdates und -einfügungen ## Synopsis Der SQL-Befehl `MERGE` ermöglicht es Benutzern, Daten in e...
Meta Keywords: die, merge, tabelle, when, matched
-->

# MERGE in SQL: Ein umfassender Leitfaden für Datenbankupdates und -einfügungen

## Synopsis
Der SQL-Befehl `MERGE` ermöglicht es Benutzern, Daten in einer Tabelle basierend auf den Daten einer anderen Tabelle effizient zu aktualisieren oder hinzuzufügen. Dies vereinfacht den Prozess des Synchronisierens von Daten und reduziert die Notwendigkeit mehrerer SQL-Anweisungen.

## Dokumentation
Der `MERGE`-Befehl, auch als "Upsert" bekannt, kombiniert die Funktionalität von `INSERT`, `UPDATE` und `DELETE` in einer einzigen Anweisung. Mit `MERGE` können Sie:
- Daten in einer Ziel-Tabelle basierend auf einer Quelle-Tabelle einfügen, aktualisieren oder löschen.
- Mehrere Bedingungen angeben, um festzulegen, wie die Daten bearbeitet werden sollen.

### Zweck
Der Hauptzweck des `MERGE`-Befehls besteht darin, die Datenintegrität zu wahren und die Effizienz der Datenverarbeitung zu steigern, indem mehrere Operationen in einer einzigen Anweisung zusammengefasst werden.

### Verwendung
Die allgemeine Syntax für den `MERGE`-Befehl lautet:

```sql
MERGE INTO Ziel_Tabelle AS Ziel
USING Quelle_Tabelle AS Quelle
ON Ziel.Schlüssel = Quelle.Schlüssel
WHEN MATCHED THEN
    UPDATE SET Ziel.Feld1 = Quelle.Feld1, Ziel.Feld2 = Quelle.Feld2
WHEN NOT MATCHED THEN
    INSERT (Feld1, Feld2) VALUES (Quelle.Feld1, Quelle.Feld2);
```

### Details
- **Ziel_Tabelle**: Die Tabelle, die aktualisiert oder in die Daten eingefügt werden sollen.
- **Quelle_Tabelle**: Die Tabelle, aus der die Daten abgerufen werden.
- **ON**: Bedingung zur Bestimmung, ob ein Datensatz übereinstimmt.
- **WHEN MATCHED**: Definiert die Update-Operation für übereinstimmende Datensätze.
- **WHEN NOT MATCHED**: Definiert die Insert-Operation für nicht übereinstimmende Datensätze.

## Beispiele
### Einfaches Beispiel
Angenommen, wir haben eine Tabelle `Mitarbeiter` und eine Tabelle `NeueDaten`.

```sql
MERGE INTO Mitarbeiter AS M
USING NeueDaten AS N
ON M.MitarbeiterID = N.MitarbeiterID
WHEN MATCHED THEN
    UPDATE SET M.Name = N.Name, M.Gehalt = N.Gehalt
WHEN NOT MATCHED THEN
    INSERT (MitarbeiterID, Name, Gehalt) VALUES (N.MitarbeiterID, N.Name, N.Gehalt);
```

### Beispiel mit Löschoperation
In diesem Beispiel entfernen wir Mitarbeiter, die nicht mehr in den `NeueDaten` vorhanden sind.

```sql
MERGE INTO Mitarbeiter AS M
USING NeueDaten AS N
ON M.MitarbeiterID = N.MitarbeiterID
WHEN MATCHED AND N.Aktiv = 0 THEN
    DELETE
WHEN MATCHED THEN
    UPDATE SET M.Name = N.Name, M.Gehalt = N.Gehalt
WHEN NOT MATCHED THEN
    INSERT (MitarbeiterID, Name, Gehalt) VALUES (N.MitarbeiterID, N.Name, N.Gehalt);
```

## Erklärung
### Häufige Fallstricke
- **Unzureichende Bedingungen**: Stellen Sie sicher, dass die ON-Bedingung korrekt ist, um unbeabsichtigte Datenänderungen zu vermeiden.
- **Fehlende Berechtigungen**: Überprüfen Sie die Berechtigungen für die Ziel- und Quelldatenbanken, um sicherzustellen, dass Sie die erforderlichen Operationen durchführen können.
- **Komplexität**: Bei sehr großen Datenmengen kann der `MERGE`-Befehl langsamer sein als separate `INSERT`- und `UPDATE`-Anweisungen. Testen Sie die Leistung in Ihrer spezifischen Umgebung.

## Ein Satz Zusammenfassung
Der SQL-Befehl `MERGE` vereinfacht die gleichzeitige Aktualisierung und Einfügung von Datensätzen in einer Tabelle, basierend auf einer anderen Tabelle.