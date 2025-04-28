<!--
Meta Description: # REVOKE in SQL: Berechtigungen und deren Entzug ## Synopsis Der SQL-Befehl REVOKE wird verwendet, um zuvor erteilte Berechtigungen von Benutzern oder...
Meta Keywords: der, die, berechtigungen, revoke, von
-->

# REVOKE in SQL: Berechtigungen und deren Entzug

## Synopsis
Der SQL-Befehl REVOKE wird verwendet, um zuvor erteilte Berechtigungen von Benutzern oder Rollen in einer Datenbank zu entziehen. Dies ist ein wichtiger Bestandteil des Berechtigungsmanagements in relationalen Datenbanksystemen.

## Dokumentation
Der REVOKE-Befehl ist ein Standard-SQL-Befehl, der es Datenbankadministratoren ermöglicht, spezifische Berechtigungen, die einem Benutzer oder einer Rolle zugewiesen wurden, zurückzunehmen. Dies ist entscheidend für die Sicherheit und Verwaltung von Datenbankressourcen, da es sicherstellt, dass nur autorisierte Benutzer auf bestimmte Daten zugreifen oder Aktionen durchführen können.

### Zweck
- **Sicherheitsmanagement**: Einschränkung des Zugriffs auf sensible Daten.
- **Rollenverwaltung**: Anpassung von Benutzerrollen und Berechtigungen.
- **Datenintegrität**: Verhindern unbefugter Änderungen an Daten.

### Verwendung
Der allgemeine Syntax für den REVOKE-Befehl lautet:

```sql
REVOKE {ALL | privilege_type [, privilege_type]...}
ON object_type object_name
FROM user_or_role;
```

- **privilege_type**: Der Typ der Berechtigung, die entzogen werden soll (z.B. SELECT, INSERT, UPDATE).
- **object_type**: Der Typ des Objekts, auf das sich die Berechtigung bezieht (z.B. TABLE, VIEW).
- **object_name**: Der Name des Objekts.
- **user_or_role**: Der Benutzer oder die Rolle, von der die Berechtigung entzogen werden soll.

## Beispiele

1. **Entzug der SELECT-Berechtigung von einem Benutzer:**

   ```sql
   REVOKE SELECT ON employees FROM user1;
   ```

   In diesem Beispiel wird dem Benutzer `user1` die Berechtigung entzogen, die `SELECT`-Operation auf der Tabelle `employees` auszuführen.

2. **Entzug mehrerer Berechtigungen:**

   ```sql
   REVOKE INSERT, UPDATE ON products FROM user2;
   ```

   Hierbei werden dem Benutzer `user2` sowohl die `INSERT`- als auch die `UPDATE`-Berechtigung auf der Tabelle `products` entzogen.

3. **Entzug aller Berechtigungen auf ein Objekt:**

   ```sql
   REVOKE ALL ON sales FROM role_sales_team;
   ```

   In diesem Fall wird der Rolle `role_sales_team` jeglicher Zugriff auf die Tabelle `sales` entzogen.

## Erklärung
Ein häufiger Fehler beim Einsatz des REVOKE-Befehls ist das Versäumnis, die richtigen Berechtigungen oder Objekttypen anzugeben. Zudem ist es wichtig zu beachten, dass REVOKE nur für Berechtigungen funktioniert, die zuvor mit GRANT erteilt wurden. Ein weiterer Punkt ist, dass der Entzug von Berechtigungen nicht rückgängig gemacht werden kann, es sei denn, die Berechtigungen werden erneut mit GRANT erteilt.

Ein weiteres "Gotcha" ist, dass beim Entzug von Berechtigungen von einer Rolle alle Mitglieder dieser Rolle die Berechtigungen verlieren, was möglicherweise unbeabsichtigte Auswirkungen auf alle Benutzer haben kann.

## Ein-Satz-Zusammenfassung
Der SQL-Befehl REVOKE dient dazu, zuvor erteilte Berechtigungen von Benutzern oder Rollen in einer Datenbank zu entziehen, um die Sicherheit und Integrität der Daten zu gewährleisten.