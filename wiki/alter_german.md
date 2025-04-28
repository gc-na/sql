<!--
Meta Description: # ALTER: SQL-Befehl zur Änderung von Datenbankobjekten ## Synopsis Der SQL-Befehl `ALTER` wird verwendet, um bestehende Datenbankobjekte wie Tabellen,...
Meta Keywords: alter, sql, von, befehl, der
-->

# ALTER: SQL-Befehl zur Änderung von Datenbankobjekten

## Synopsis
Der SQL-Befehl `ALTER` wird verwendet, um bestehende Datenbankobjekte wie Tabellen, Sichten, Indizes und Datenbanken zu ändern. Mit `ALTER` können Sie Strukturen anpassen, neue Spalten hinzufügen oder bestehende löschen.

## Dokumentation
Der `ALTER`-Befehl ist ein grundlegendes Werkzeug in SQL für Datenbankadministratoren und Entwickler. Er ermöglicht die Modifikation von Datenbankstrukturen, ohne dass die bestehenden Daten verloren gehen. Der Befehl kann in verschiedenen Kontexten verwendet werden, darunter:

- **ALTER TABLE**: Zum Ändern von Tabellenstrukturen, etwa zum Hinzufügen, Ändern oder Löschen von Spalten.
- **ALTER VIEW**: Zum Aktualisieren der Definition einer Sicht.
- **ALTER INDEX**: Zum Anpassen von Indizes.
- **ALTER DATABASE**: Zum Ändern von Datenbankeinstellungen.

### Verwendung
Die allgemeine Syntax für den `ALTER`-Befehl variiert je nach dem Objekt, das geändert werden soll. Hier sind einige Beispiele:

- **ALTER TABLE**:
  ```sql
  ALTER TABLE tabellenname ADD spaltenname DATENTYP;
  ALTER TABLE tabellenname DROP COLUMN spaltenname;
  ALTER TABLE tabellenname ALTER COLUMN spaltenname DATENTYP;
  ```

- **ALTER VIEW**:
  ```sql
  ALTER VIEW sichtname AS SELECT spalte1, spalte2 FROM tabellenname WHERE bedingung;
  ```

- **ALTER INDEX**:
  ```sql
  ALTER INDEX indexname REBUILD;
  ```

- **ALTER DATABASE**:
  ```sql
  ALTER DATABASE datenbankname SET OPTION = WERT;
  ```

## Beispiele
Hier sind einige konkrete Beispiele für den `ALTER`-Befehl:

1. **Spalte hinzufügen**:
   ```sql
   ALTER TABLE Kunden ADD Geburtsdatum DATE;
   ```

2. **Spalte löschen**:
   ```sql
   ALTER TABLE Kunden DROP COLUMN Geburtsdatum;
   ```

3. **Spalte ändern**:
   ```sql
   ALTER TABLE Kunden ALTER COLUMN Nachname VARCHAR(100);
   ```

4. **Sicht aktualisieren**:
   ```sql
   ALTER VIEW AktiveKunden AS SELECT * FROM Kunden WHERE Aktiver = 1;
   ```

## Erklärung
Beim Einsatz des `ALTER`-Befehls gibt es einige häufige Fallstricke und Punkte, die beachtet werden sollten:

- **Datenverlust**: Das Löschen von Spalten kann zu einem dauerhaften Verlust von Daten führen. Stellen Sie sicher, dass Sie eine Sicherung haben.
- **Abhängigkeiten**: Änderungen an Tabellen, wie das Löschen von Spalten oder das Ändern von Datentypen, können bestehende Abfragen und Anwendungen beeinflussen. Überprüfen Sie alle Abhängigkeiten.
- **Transaktionen**: Bei größeren Änderungen sollte der `ALTER`-Befehl in einer Transaktion verwendet werden, um im Falle eines Fehlers zurückgerollt werden zu können.
- **Dauer**: Einige `ALTER`-Operationen können je nach Größe der Tabelle und Anzahl der betroffenen Daten sehr lange dauern.

## Zusammenfassung in einem Satz
Der SQL-Befehl `ALTER` ermöglicht die flexible Anpassung von Datenbankobjekten, um deren Struktur und Eigenschaften zu ändern.