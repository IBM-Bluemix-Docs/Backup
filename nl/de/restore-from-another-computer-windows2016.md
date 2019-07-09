---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, restore

subcollection: Backup

---

# Job aus anderem Computer unter Windows 2016 wiederherstellen
{: #restorefromother2016}

Verwenden Sie die nachfolgenden Schritte, um eine Dateiwiederherstellung aus einem anderen Computer mithilfe von Windows Central Control durchzuführen.

1. Aktivieren Sie die Fernsteuerung Ihres Windows 2016-Servers über RDP.
2. Öffnen Sie Central Control.
3. Klicken Sie mit der rechten Maustaste auf **Agent** und klicken Sie dann auf **Agentenkonfiguration**.
4. Entfernen Sie die aktuellen Vaulteinstellungen aus Central Control, indem Sie den Eintrag auswählen und auf **Löschen** klicken.
5. Klicken Sie auf **Neu** und wählen Sie in der nächsten Anzeige die Option **Zuvor registrierten Computer erneut registrieren** aus. Klicken Sie auf **Weiter**.
6. Geben Sie die Netzadresse ein, klicken Sie auf **Hinzufügen** und dann auf **Weiter**.
7. Geben Sie die neuen Portwerte ein, klicken Sie auf **Hinzufügen** und dann auf **Weiter**.
8. Geben Sie in der Anzeige 'Verbindungseinstellungen' die gewünschte Anzahl der Sekunden/Minuten ein.
9. Geben Sie in der Anzeige 'Authentifizierung' Ihre Berechtigungsnachweise ein und klicken Sie dann auf **Weiter**.
10. Im Fenster 'Registrierte Computer' wird nun der Hostname Ihres Servers angezeigt. Klicken Sie auf **Weiter**.
11.	Wenn der Assistent für die Vaultkonfiguration alle Informationen von Ihnen erfasst hat, klicken Sie auf **Fertigstellen**, um die Registrierung abzuschließen.
12. Bestätigen Sie bei der entsprechenden Eingabeaufforderung, dass Sie die erneute Registrierung fortsetzen wollen.
13. Klicken Sie nach Abschluss der Registrierung in der Menüleiste auf **Wiederherstellung**.
9.	Wählen Sie die entsprechende Sicherungsgruppe aus und geben Sie das Verschlüsselungskennwort ein. Klicken Sie auf **Weiter**.
10.	Wählen Sie die Dateien aus, die Sie wiederherstellen wollen, wählen Sie dann die Standardoptionen aus und klicken Sie auf **Fertigstellen**.
11.	Entfernen Sie nach Abschluss der Wiederherstellung die Vaultregistrierung und nehmen Sie eine erneute Registrierung mit den aktuellen Kontoinformationen für die Vault vor.
