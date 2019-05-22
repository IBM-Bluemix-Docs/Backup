---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, port information, configure, configuring,

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Ports für Kommunikation zwischen dem Backup-Agenten und {{site.data.keyword.backup_notm}}-Portal konfigurieren
{: #portinfo}

Der {{site.data.keyword.backup_full}}-Agent, der auf Ihrem Server installiert ist, muss in der Lage sein, mit dem von Ihnen erworbenen Vault zu kommunizieren. Die Hostinformationen zu Director für ein {{site.data.keyword.backup_notm}}-Benutzerkonto stehen im [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external} und in der [{{site.data.keyword.cloud_notm}}-Konsole](https://{DomainName}){: external} zur Verfügung.

Registrieren Sie Agenten beim {{site.data.keyword.backup_notm}}-Portal und den Director-Instanzen immer mit FQDN, weil die IP-Adresse für diese Services sich möglicherweise ändern.

Ihre Server müssen mit dem {{site.data.keyword.backup_notm}}-Portal und allen AMP-Proxy-Servern kommunizieren, damit das {{site.data.keyword.backup_notm}}-Portal ordnungsgemäß funktioniert, und zwar ungeachtet des Rechenzentrumsstandorts.

```
https://evregister.service.softlayer.com TCP 8086,8087
```

Weitere AMP-Proxy-Server können bei Bedarf hinzugefügt werden, um mehr {{site.data.keyword.backup_notm}}-Agenten auszuführen, die beim {{site.data.keyword.backup_notm}}-Portal registriert sind.

TCP-Port 8086, 8087 muss Zugriff auf 10.0.0.0/8 besitzen.
{:important}

Falls Sie restriktivere Firewallregeln verwenden müssen, verlieren Sie möglicherweise den Zugriff auf das {{site.data.keyword.backup_notm}}-Portal, wenn die Infrastruktur erweitert wird. Gegenwärtig müssen Ihre Server mindestens den Zugriff auf die Teilnetze 10.0.82.0/24 und 10.2.118.0/24 für die TCP-Ports 8086, 8087 zulassen. Weitere Teilnetze können künftig bei Bedarf hinzugefügt werden.

## Kostenpflichtig

*{{site.data.keyword.backup_notm}}-Portal und AMP-Proxy-Server*

- `https://ev-webcc01.service.softlayer.com` [10.0.82.12] 8086, 8087
- `https://evregister.service.softlayer.com` [10.0.82.12] 8086, 8087

*Kostenpflichtige AMP-Proxy-Server*

- evwebamp0901.service.softlayer.com [10.2.118.12] 8087
- evwebamp0902.service.softlayer.com [10.2.118.13] 8087
- evwebamp0903.service.softlayer.com [10.2.118.14] 8087
- evwebamp0904.service.softlayer.com [10.2.118.15] 8087
- evwebamp0905.service.softlayer.com [10.2.118.16] 8087
- evwebamp0906.service.softlayer.com [10.2.118.17] 8087
- evwebamp0907.service.softlayer.com [10.2.118.18] 8087
- evwebamp0908.service.softlayer.com [10.2.118.19] 8087

## US-Bundesumgebung

*{{site.data.keyword.backup_notm}}-Portal und AMP-Proxy*

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087

Der Agent muss den eingehenden TCP-Port 2548 im privaten Netz zulassen. Diese Einstellung ermöglicht es Central Control und dem {{site.data.keyword.backup_notm}}-Portal, im Agenten eine Verbindung zu dessen Verwaltung herzustellen. Ältere Versionen von EVault nutzten Port 808.

Der {{site.data.keyword.backup_notm}}-Management-Port (2548)  kann durch eine Aktualisierung des Registrierungsschlüssels unter `HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber` (was einem `dword` entspricht) in Windows-Betriebssystemen geändert werden.

In Bezug auf die Verbindungseinstellungen bestehen häufig Unklarheiten hinsichtlich des Unterschieds zwischen der Central Control-Desktopinstanz und dem Agenten. Der auf dem Server implementierte Agent stellt eine Verbindung zu den {{site.data.keyword.backup_notm}}-Servern her, während die auf dem Desktop verwendete Central Control-Instanz Verbindungen zu Ihrem Server herstellt und hierbei die Serveradresse und die Serverberechtigungsnachweise für den Zugriff verwendet.
{:tip}
