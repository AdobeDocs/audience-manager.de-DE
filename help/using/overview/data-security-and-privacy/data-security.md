---
description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-description: Audience Manager takes data security and privacy very seriously. We work to keep our systems secure and protect your valuable data.
seo-title: Datensicherheit
solution: Audience Manager
title: Datensicherheit
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
translation-type: tm+mt
source-git-commit: 34884e3212d50237c73fdc6aa163d90c29a642f5

---


# Datensicherheit {#data-security}

Audience Manager nimmt Datensicherheit und Datenschutz sehr ernst. Wir arbeiten daran, unsere Systeme sicher zu halten und Ihre wertvollen Daten zu schützen.

Audience Manager security practices include external and internal audits, activity logging, training, and other procedures designed to help protect our systems and your valuable data. Wir glauben, dass ein sicheres Produkt dazu beiträgt, das Vertrauen der Kunden in uns aufzubauen und zu erhalten.

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

**** Sicherheitsschulung:  Intern gilt unser Engagement für Sicherheit auch für Entwickler, die an unserem Produkt arbeiten. Adobe provides formal training to developers on how to build secure applications and services.

**** Secure Access:  Audience Manager requires strong passwords to log on to the system. See password requirements.[](../../reference/password-requirements.md)

## Privacy and Personally Identifiable Information (PII) {#pii}

Processes that help keep personal information safe. For additional privacy information, see the Adobe Privacy Center.[](https://www.adobe.com/privacy/advertising-services.html)

**** PII Data:  Audience Manager contractually prohibits customers and data partners from sending PII information into our system. Darüber hinaus enthält oder verwendet die Unique User ID (UUID) keine PII-Daten als Teil des ID-Generierungsalgorithmus.

**** IP Addresses:  Audience Manager does collect IP addresses. IP addresses are used in data-processing and log-aggregation processes. They are also required for geographic/location look-ups and targeting. Darüber hinaus werden alle IP-Adressen innerhalb der gespeicherten Protokolldateien innerhalb von 90 Tagen verschleiert.

## Data Partitioning {#data-partitioning}

Processes that help protect data owned by individual clients.

**** Eigenschaftsdatenunterteilung:  Ihre Daten (Eigenschaften, IDs usw.) vom Client partitioniert. Dadurch wird verhindert, dass versehentlich Informationen zwischen verschiedenen Kunden angezeigt werden. So werden z. B. Eigenschaftsdaten in Cookies vom Kunden getrennt und in einer kundenspezifischen Subdomäne gespeichert. Es kann nicht versehentlich von einem anderen Audience Manager-Client gelesen oder verwendet werden. Furthermore, trait data stored in the  is also partitioned by customer. [!UICONTROL Profile Cache Servers (PCS)] Dadurch wird verhindert, dass andere Clients Ihre Daten versehentlich in einem Ereignisaufruf oder einer anderen Anforderung verwenden.

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

[!DNL HTTP Strict-Transport-Security (HSTS)] ist ein branchenweiter Web-Sicherheitsmechanismus, der hilft, vor Cookie-Hijacking und Protokolldowngrade-Angriffen zu schützen.

Die Richtlinie weist den Webbrowser an, dass nach einem sicheren [!DNL HTTPS] Aufruf an eine bestimmte Domäne keine weiteren unsicheren Aufrufe ([!DNL HTTP]) in diese Domäne zulässig sein sollten. This protects against man-in-the-middle attacks, where an attacker might try to downgrade  calls to unsecured  calls.”[!DNL HTTPS][!DNL HTTP]

Diese Richtlinie verbessert die Datensicherheit zwischen Clients und Adobe [Edge](../../reference/system-components/components-edge.md) -Servern.

### Beispiel {#hsts-example}

Let's say the  domain sends trafic to the  via . `yourcompany.demdex.com`[!DNL DCS][!DNL HTTP] [!DNL HSTS] upgrades the calls to use  instead, and all subsequent  calls coming from  will use  instead of .[!DNL HTTPS][!DNL DCS]`yourcompany.demdex.com`[!DNL HTTPS][!DNL HTTP]

See HTTP Strict Transport Security - Wikipedia for more information about HSTS.[](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)
