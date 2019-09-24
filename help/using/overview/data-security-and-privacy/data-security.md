---
description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-title: Datensicherheit
solution: Audience Manager
title: Datensicherheit
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 9e1abb305c66a4adf6a42a7873144222491692f9

---


# Datensicherheit {#data-security}

Audience Manager nimmt Datensicherheit und Datenschutz sehr ernst. Wir arbeiten daran, unsere Systeme sicher zu halten und Ihre wertvollen Daten zu schützen.

Zu den Sicherheitspraktiken von Audience Manager gehören externe und interne Audits, Aktivitätsprotokollierung, Schulungen und andere Verfahren zum Schutz unserer Systeme und Ihrer wertvollen Daten. Wir glauben, dass ein sicheres Produkt dazu beiträgt, das Vertrauen der Kunden in uns aufzubauen und zu erhalten.

In Audience Manager denken wir an Sicherheit in drei Hauptkategorien:

| Sicherheitstyp | Unterstützung für |
|---|---|
| **Informationssicherheit** | Authentifizierungs-, Verschlüsselungs- und Datenspeicherverfahren auf Unternehmensebene |
| **Datenleck/Transparenz** | Tiefer und umsetzbarer Einblick in Aktivitäten vor Ort, die Datenleckage verursachen oder zu Datenlecks beitragen |
| **Prozess-/Richtlinienverbesserungen** | Kunden durch Zusammenarbeit mit branchenüblichen Best Practices für Datenschutz und Datensicherheit |

## Systeme, Schulung und Zugriff {#systems-training-access}

Prozesse, die unser System und Ihre Daten schützen.

**** Überprüfung der externen Sicherheit:  Audience Manager überprüft die Sicherheit jährlich und vierteljährlich.

* Jährlich: Einmal im Jahr wird Audience Manager einem vollständigen Penetrationstest unterzogen, der von einem unabhängigen Drittanbieter durchgeführt wird. Der Test wurde entwickelt, um Sicherheitslücken in der Anwendung zu identifizieren. Zu den Tests gehören das Prüfen auf Site-übergreifende Skripterstellung, SQL-Injektionen, Formularparametermanipulation und andere Schwachstellen auf Anwendungsebene.
* Vierteljährlich: Jedes Quartal überprüfen interne Teams auf Sicherheitslücken. Zu diesen Tests gehören Netzwerkprüfungen auf offene Ports und Service-Schwachstellen.

**** Systemsicherheit:  Um die Sicherheit und den Schutz von Daten zu gewährleisten, muss Audience Manager Folgendes tun:

* Blockiert Anfragen von nicht autorisierten IP-Adressen.
* Schützt Daten hinter Firewalls, VPNs und mit Virtual Private Cloud-Speicher.
* Verfolgt Änderungen in den Kunden- und Steuerungsdatenbanken mit auslöserbasierter Prüfprotokollierung. Diese Protokolle verfolgen alle Änderungen auf Datenbankebene, einschließlich der Benutzer-ID und IP-Adresse, von der aus Änderungen vorgenommen werden.

**** Security Assets:  Audience Manager has a dedicated network operations team that monitors firewalls and intrusion-detection devices. Only key personnel have access to our security technology and data.

**** Security Training:  Internally, our commitment to security extends to developers who work on our product. Adobe provides formal training to developers on how to build secure applications and services.

**** Secure Access:  Audience Manager requires strong passwords to log on to the system. See password requirements.[](../../reference/password-requirements.md)

## Privacy and Personally Identifiable Information (PII) {#pii}

Prozesse, die dazu beitragen, die Sicherheit personenbezogener Daten zu gewährleisten. For additional privacy information, see the Adobe Privacy Center.[](https://www.adobe.com/privacy/advertising-services.html)

**** PII Data:  Audience Manager contractually prohibits customers and data partners from sending PII information into our system. Additionally, the Unique User ID (UUID) does not contain or use PII data as part of the ID-generation algorithm.

**** IP Addresses:  Audience Manager does collect IP addresses. IP addresses are used in data-processing and log-aggregation processes. They are also required for geographic/location look-ups and targeting. Additionally, all IP addresses within retained log files are obfuscated within 90 days.

## Datenunterteilung {#data-partitioning}

Prozesse, die dazu beitragen, Daten einzelner Kunden zu schützen.

**** Eigenschaftsdatenunterteilung:  Ihre Daten (Eigenschaften, IDs usw.) vom Client partitioniert. Dadurch wird verhindert, dass versehentlich Informationen zwischen verschiedenen Kunden angezeigt werden. So werden z. B. Eigenschaftsdaten in Cookies vom Kunden getrennt und in einer kundenspezifischen Subdomäne gespeichert. Es kann nicht versehentlich von einem anderen Audience Manager-Client gelesen oder verwendet werden. Darüber hinaus [!UICONTROL Profile Cache Servers (PCS)] werden die im System gespeicherten Eigenschaftsdaten auch vom Kunden aufgeteilt. Dadurch wird verhindert, dass andere Clients Ihre Daten versehentlich in einem Ereignisaufruf oder einer anderen Anforderung verwenden.

**** Datenunterteilung in Berichten:  Client-IDs sind Teil des identifizierenden Schlüssels in allen Berichtstabellen, und Berichtsabfragen werden nach ID gefiltert. Dadurch wird verhindert, dass Ihre Daten in den Berichten eines anderen Audience Manager-Kunden angezeigt werden.

## Inbound Server-to-Server (S2S) Transfers {#inbound-s2s}

Adobe Audience Manager unterstützt zwei Hauptmethoden zum Übertragen von S2S-Dateien an Bord zu unseren Systemen:

Beide Methoden sind unter Berücksichtigung der Sicherheit unserer Kunden- und Partnerdaten konzipiert, während die Daten zwischen ihren Systemen und unserem System liegen.

**** SFTP: Bei der SFTP-Option wählen die meisten Kunden die Bereitstellung von Dateien über das Secure FTP (SFTP)-Protokoll, das das Secure Shell (SSH)-Protokoll verwendet. Diese Methode stellt sicher, dass Dateien während des Fluges zwischen den Systemen des Kunden und dem Adobe-System verschlüsselt werden. Für jeden Kunden erstellen wir auf unseren SFTP-Servern einen per Gefängnis geschützten Speicherort, der an ein Benutzerkonto auf diesem System gebunden ist. Nur die autorisierten und privilegierten internen Systembenutzer des Kunden können auf diesen per Knopfdruck geschützten Speicherort zugreifen. Dieses Gefängnis ist für andere Kunden nie zugänglich.

**** Amazon Web Services S3 über HTTPS: Für die S3-Auslieferungsoption empfehlen wir allen Kunden, ihre S3-Clients so zu konfigurieren, dass die HTTPS-Verschlüsselungsmethode für Dateiübertragungen verwendet wird (dies ist nicht die Standardeinstellung, daher muss sie explizit konfiguriert werden). Die HTTPS-Option wird sowohl vom s3cmd-Befehlszeilenwerkzeug als auch von den S3-Bibliotheken unterstützt, die in jeder gängigen Programmiersprache verfügbar sind. Bei aktivierter HTTPS-Option werden die Daten des Kunden während des Fluges zu unseren Systemen verschlüsselt. Für jeden Kunden erstellen wir einen separaten S3-Behälter-Unterordner, auf den nur die Anmeldeinformationen dieses Kunden und die unserer internen Systembenutzer zugreifen können.

Informationen zum Hinzufügen der PGP-Verschlüsselung zu Ihren Datendateien finden Sie unter [File PGP Encryption for Inbound Data Types](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## Schutz von Daten durch Escapezeichen {#escaping-data}

Beachten Sie, dass ausgehende Daten [!DNL Audience Manager] nicht entkommen, um sie gegen mögliche Site-übergreifende Skripterstellung (XSS) usw. zu schützen. Es liegt in der Verantwortung des Kunden, eingehenden Daten zu entkommen.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] ist ein Sicherheitsrichtlinienmechanismus für Web-Seiten, der hilft, sich vor Cookie-Hijacking und Downgrade-Angriffen zu schützen, indem kein Traffic zugelassen [!DNL HTTP] wird und der alle [!DNL HTTP] Traffic transparent aktualisiert [!DNL HTTPS].

This policy improves data security between clients and Adobe Edge servers.

### Beispiel {#hsts-example}

When trying to access ,  will automatically upgrade the request to  , in case the browser doesn’t automatically request the  domain.`http://bank.demdex.com`[!DNL HSTS]`https://bank.demdex.com`[!DNL HTTPS]

See HTTP Strict Transport Security - Wikipedia for more information about HSTS.[](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)
