---
description: Audience Manager nimmt Datensicherheit und Datenschutz sehr ernst. Wir arbeiten daran, unsere Systeme sicher zu halten und Ihre wertvollen Daten zu schützen.
seo-description: Audience Manager nimmt Datensicherheit und Datenschutz sehr ernst. Wir arbeiten daran, unsere Systeme sicher zu halten und Ihre wertvollen Daten zu schützen.
seo-title: Datensicherheit
solution: Audience Manager
title: Datensicherheit
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 91444ad943fcd020c83e522922d67ef400bf8824

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

## Systems, Training, and Access {#systems-training-access}

Prozesse, die unser System und Ihre Daten schützen.

**** External Security Validation:  Audience Manager tests security on an annual and quarterly basis.

* Yearly: Once a year, Audience Manager undergoes a full penetration test conducted by an independent third-party company. The test is designed to identify security vulnerabilities in the application. The tests include scanning for cross-site scripting, SQL injections, form parameter manipulation, and other application-level vulnerabilities.
* Quarterly: Once each quarter, internal teams check for security vulnerabilities. Zu diesen Tests gehören Netzwerkprüfungen auf offene Ports und Service-Schwachstellen.

**Systems Security:**  To help keep data safe and private, Audience Manager:

* Blockiert Anfragen von nicht autorisierten IP-Adressen.
* Schützt Daten hinter Firewalls, VPNs und mit Virtual Private Cloud-Speicher.
* Verfolgt Änderungen in den Kunden- und Steuerungsdatenbanken mit auslöserbasierter Prüfprotokollierung. These logs track all changes at the database level, including the user ID and IP address from which changes are made.

**Security Assets:**  Audience Manager has a dedicated network operations team that monitors firewalls and intrusion-detection devices. Nur wichtige Mitarbeiter haben Zugang zu unserer Sicherheitstechnik und unseren Daten.

**Security Training:**  Internally, our commitment to security extends to developers who work on our product. Adobe bietet Entwicklern formelle Schulungen zum Erstellen sicherer Anwendungen und Dienste.

**** Sicherer Zugriff:  Audience Manager erfordert sichere Kennwörter, um sich beim System anzumelden. Siehe [Kennwortanforderungen](../../reference/password-requirements.md).

## Datenschutz und personenbezogene Daten (PII) {#pii}

Prozesse, die dazu beitragen, die Sicherheit personenbezogener Daten zu gewährleisten. Weitere Informationen zum Datenschutz finden Sie im [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

**** PII-Daten:  Audience Manager verbietet Kunden und Datenpartnern vertraglich, PII-Informationen an unser System zu senden. Darüber hinaus enthält oder verwendet die Unique User ID (UUID) keine PII-Daten als Teil des ID-Generierungsalgorithmus.

**** IP-Adressen:  Audience Manager erfasst IP-Adressen. IP-Adressen werden in Datenverarbeitungs- und Protokollaggregationsprozessen verwendet. Sie sind auch für geografische/Standortsuche und Targeting erforderlich. Darüber hinaus werden alle IP-Adressen innerhalb der gespeicherten Protokolldateien innerhalb von 90 Tagen verschleiert.

## Datenunterteilung {#data-partitioning}

Prozesse, die dazu beitragen, Daten einzelner Kunden zu schützen.

**** Eigenschaftsdatenunterteilung:  Ihre Daten (Eigenschaften, IDs usw.) vom Client partitioniert. Dadurch wird verhindert, dass unbeabsichtigte Informationen zwischen verschiedenen Kunden angezeigt werden. So werden z. B. Eigenschaftsdaten in Cookies vom Kunden getrennt und in einer kundenspezifischen Subdomäne gespeichert. Es kann nicht versehentlich von einem anderen Audience Manager-Client gelesen oder verwendet werden. Darüber hinaus [!UICONTROL Profile Cache Servers (PCS)] werden die im System gespeicherten Eigenschaftsdaten auch vom Kunden aufgeteilt. Dadurch wird verhindert, dass andere Clients Ihre Daten versehentlich in einem Ereignisaufruf oder einer anderen Anforderung verwenden.

**** Datenunterteilung in Berichten:  Client-IDs sind Teil des identifizierenden Schlüssels in allen Berichtstabellen, und Berichtsabfragen werden nach ID gefiltert. Dadurch wird verhindert, dass Ihre Daten in den Berichten eines anderen Audience Manager-Kunden angezeigt werden.

## Inbound Server-to-Server (S2S) Transfers {#inbound-s2s}

Adobe Audience Manager unterstützt zwei Hauptmethoden zum Übertragen von S2S-Dateien an Bord zu unseren Systemen:

Beide Methoden sind unter Berücksichtigung der Sicherheit unserer Kunden- und Partnerdaten konzipiert, während die Daten zwischen ihren Systemen und unserem System liegen.

**** SFTP: Bei der SFTP-Option wählen die meisten Kunden die Bereitstellung von Dateien über das Secure FTP (SFTP)-Protokoll, das das Secure Shell (SSH)-Protokoll verwendet. Diese Methode stellt sicher, dass Dateien während des Fluges zwischen den Systemen des Kunden und dem Adobe-System verschlüsselt werden. Für jeden Kunden erstellen wir auf unseren SFTP-Servern einen per Gefängnis geschützten Speicherort, der an ein Benutzerkonto auf diesem System gebunden ist. Only the customer's credentialed and privileged internal system users can access this jailed drop-box location. Dieses Gefängnis ist für andere Kunden nie zugänglich.

**** Amazon Web Services S3 über HTTPS: Für die S3-Auslieferungsoption empfehlen wir allen Kunden, ihre S3-Clients so zu konfigurieren, dass die HTTPS-Verschlüsselungsmethode für Dateiübertragungen verwendet wird (dies ist nicht die Standardeinstellung, daher muss sie explizit konfiguriert werden). The HTTPS option is supported both by the s3cmd command line tool as well as the S3 libraries available in every major programming language. With this HTTPS option enabled, customer's data is encrypted while in flight to our systems. Für jeden Kunden erstellen wir einen separaten S3-Behälter-Unterordner, auf den nur die Anmeldeinformationen dieses Kunden und die unserer internen Systembenutzer zugreifen können.

To add PGP encryption to your data files, see File PGP Encryption for Inbound Data Types.[](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md)

## Protecting Data by Escaping {#escaping-data}

Beachten Sie, dass ausgehende Daten [!DNL Audience Manager] nicht entkommen, um sie gegen mögliche Site-übergreifende Skripterstellung (XSS) usw. zu schützen. Es liegt in der Verantwortung des Kunden, eingehenden Daten zu entkommen.

## HTTP Strict-Transport-Security (#hsts)

[!DNL HTTP Strict-Transport-Security (HSTS)] ist ein Sicherheitsrichtlinienmechanismus für Web-Seiten, der hilft, sich vor Cookie-Hijacking und Downgrade-Angriffen zu schützen, indem kein Traffic zugelassen [!DNL HTTP] wird und der alle [!DNL HTTP] Traffic transparent aktualisiert [!DNL HTTPS].

Diese Richtlinie verbessert die Datensicherheit zwischen Clients und Adobe Edge-Servern.

### Beispiel {#hsts-example}

Wenn Sie versuchen, Zugriff zu erhalten `http://bank.demdex.com`, [!DNL HSTS] wird die Anforderung automatisch aktualisiert, `https://bank.demdex.com`falls der Browser die [!DNL HTTPS] Domäne nicht automatisch anfordert.

Weitere Informationen zu HSTS finden Sie unter [HTTP Strict Transport Security - Wikipedia](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security) .
