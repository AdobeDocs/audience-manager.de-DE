---
description: Audience Manager nimmt Datensicherheit und Datenschutz sehr ernst. Wir arbeiten daran, die Sicherheit unserer Systeme aufrechtzuhalten und Ihre wichtigen Daten zu schützen.
seo-description: Audience Manager nimmt Datensicherheit und Datenschutz sehr ernst. Wir arbeiten daran, die Sicherheit unserer Systeme aufrechtzuhalten und Ihre wichtigen Daten zu schützen.
seo-title: Datensicherheit in Audience Manager
solution: Audience Manager
title: Datensicherheit in Audience Manager
uuid: 33ad19ca-4690-4d97-853b-1882d7d4ac01
feature: Data Governance und Datenschutz
exl-id: 94b70250-dca3-4c50-b4dd-bc37178a587e
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1028'
ht-degree: 98%

---

# Datensicherheit in Audience Manager {#data-security}

Audience Manager nimmt Datensicherheit und Datenschutz sehr ernst. Wir arbeiten daran, die Sicherheit unserer Systeme aufrechtzuhalten und Ihre wichtigen Daten zu schützen.

Zu den Sicherheitsmaßnahmen von Audience Manager gehören externe und interne Audits, die Protokollierung von Aktivitäten, Schulungen und andere Verfahren zum Schutz unserer Systeme und Ihrer wichtigen Daten. Wir glauben, dass ein sicheres Produkt dazu beiträgt, das Vertrauen der Kunden in uns aufzubauen und aufrechtzuerhalten.

In Audience Manager denken wir über Sicherheit in drei Kategorien nach:

| Sicherheitstyp | Unterstützung für |
|---|---|
| **Informationssicherheit** | Verfahren zur Authentifizierung, Verschlüsselung und Datenspeicherung auf Unternehmensebene |
| **Datenlecks/Transparenz** | Tiefgreifende und umsetzbare Einblicke in On-site-Aktivitäten, die Datenlecks darstellen oder dazu beitragen |
| **Prozess-/Richtlinienverbesserungen** | Clients, durch Zusammenarbeit mit branchenüblichen Best Practices für Datenschutz und Datensicherheit |

## Systeme, Schulung und Zugriff {#systems-training-access}

Prozesse, die dazu beitragen, unser System und Ihre Daten sicher zu halten.

**Externe Sicherheitsvalidierung:** Audience Manager überprüft die Sicherheit jährlich und vierteljährlich.

* Jährlich: Einmal im Jahr wird der Audience Manager einem vollständigen Penetrationstest unterzogen, der von einem unabhängigen Drittunternehmen durchgeführt wird. Der Test dient dazu, Sicherheitslücken in der Anwendung zu identifizieren. Die Tests umfassen das Scannen nach Cross-Site-Scripting, SQL-Injektionen, Manipulation von Formularparametern und andere Schwachstellen auf Anwendungsebene.
* Vierteljährlich: Einmal pro Quartal prüfen interne Teams, ob Sicherheitslücken bestehen. Diese Tests umfassen Netzwerk-Scans auf offene Ports und Dienstschwachstellen.

**Systemsicherheit:** Um Daten sicher und privat zu halten, bietet Audience Manager:

* Blockierung von Anfragen von nicht autorisierten IP-Adressen.
* Schutz der Daten hinter Firewalls, VPNs und mit Virtual Private Cloud-Datenspeicherung.
* Verfolgung von Änderungen in den Kunden- und Steuerungsdatenbanken mit Trigger-basierter Prüfprotokollierung. Diese Protokolle verfolgen alle Änderungen auf Datenbankebene, einschließlich der Benutzer-ID und IP-Adresse, von denen aus Änderungen vorgenommen werden.

**Sicherheitselemente:** Audience Manager verfügt über ein spezielles Team für den Netzwerkbetrieb, das Firewalls und Geräte zur Angriffserkennung (Intrusion Detection) überwacht. Nur Schlüsselpersonal hat auf unsere Sicherheitstechnologie und Daten Zugriff.

**Sicherheitsschulungen:** Intern erstreckt sich unser Engagement für die Sicherheit auch auf die Entwickler, die an unserem Produkt arbeiten. Adobe bietet Entwicklern formelle Schulungen zum Erstellen sicherer Anwendungen und Dienste.

**Sicherer Zugriff:** Audience Manager erfordert sichere Passwörter, um sich beim System anzumelden. Siehe [Passwortanforderungen](../../reference/password-requirements.md).

## Datenschutz und personenbezogene Daten (PII) {#pii}

Prozesse, die dazu beitragen, die Sicherheit personenbezogener Daten zu gewährleisten. Weitere Informationen zum Datenschutz finden Sie im [Datenschutzzentrum von Adobe](https://www.adobe.com/de/privacy/advertising-services.html).

**Personenbezogene Daten:** Audience Manager untersagt Kunden und Datenpartnern vertraglich, personenbezogene Daten an unser System zu senden. Darüber hinaus enthält oder verwendet die Unique User ID (UUID) keine personenbezogenen Daten im ID-Generierungsalgorithmus.

**IP-Adressen:** Audience Manager erfasst IP-Adressen. IP-Adressen werden in Datenverarbeitungs- und Protokollaggregationsprozessen verwendet. Sie sind auch für die geografische/Standortsuche und Targeting erforderlich. Darüber hinaus werden alle IP-Adressen innerhalb der gespeicherten Protokolldateien innerhalb von 90 Tagen verschleiert.

## Datenpartitionierung {#data-partitioning}

Prozesse zum Schutz der Daten einzelner Clients.

**Partitionierung von Eigenschaftsdaten:**  Ihre Daten ([!UICONTROL traits], IDs usw.) werden nach Client partitioniert. Dies hilft, eine versehentliche Offenlegung von Informationen zwischen verschiedenen Clients zu verhindern. Beispielsweise werden Eigenschaftsdaten in Cookies nach Kunde partitioniert und in einer Client-spezifischen Subdomäne gespeichert. Sie können nicht versehentlich von einem anderen Audience Manager-Client gelesen oder verwendet werden. Darüber hinaus werden die in [!UICONTROL Profile Cache Servers (PCS)] gespeicherten Eigenschaftsdaten auch nach Kunde partitioniert. Dadurch wird verhindert, dass andere Clients Ihre Daten versehentlich bei einem Ereignisaufruf oder einer anderen Anfrage verwenden.

**Datenpartitionierung in Berichten:** Client-IDs sind Teil des Identifizierungsschlüssels in allen Berichtstabellen, und Berichtsabfragen werden nach ID gefiltert. Dadurch wird verhindert, dass Ihre Daten in den Berichten eines anderen Audience Manager-Kunden angezeigt werden.

## Eingehende Server-to-Server (S2S)-Übertragungen {#inbound-s2s}

Adobe Audience Manager unterstützt zwei Hauptmethoden zum Übertragen von integrierten S2S-Datendateien auf unsere Systeme:

Bei beiden Methoden steht die Sicherheit der Daten unserer Kunden und Partner im Vordergrund, während die Daten zwischen ihren Systemen und unserem System übertragen werden.

**SFTP:** Bei der SFTP-Option stellen die meisten Kunden Dateien über das SFTP-Protokoll (Secure FTP) bereit, welches das SSH-Protokoll (Secure Shell) verwendet. Diese Methode stellt sicher, dass Dateien während der Übertragung zwischen den Systemen des Kunden und dem Adobe-System verschlüsselt werden. Für jeden Kunden erstellen wir auf unseren SFTP-Servern einen gesicherten Dropbox-Speicherort, der an ein Benutzerkonto auf diesem System gebunden ist. Nur die autorisierten und berechtigten internen Systembenutzer des Kunden können auf diesen gesicherten Dropbox-Speicherort zugreifen. Dieser gesicherter Speicherort ist für andere Kunden niemals zugänglich.

**[!UICONTROL Amazon Web Services S3]über HTTPS:** Für die Bereitstellungsoption über S3 empfehlen wir allen Kunden, ihre S3-Clients so zu konfigurieren, dass sie die HTTPS-Verschlüsselungsmethode für Dateiübertragungen verwenden (dies ist nicht die Standardeinstellung, daher muss sie explizit konfiguriert werden). Die HTTPS-Option wird sowohl vom Befehlszeilentool s3cmd als auch von den S3-Bibliotheken unterstützt, die in allen wichtigen Programmiersprachen verfügbar sind. Wenn diese HTTPS-Option aktiviert ist, werden die Daten des Kunden während der Übertragung auf unsere Systeme verschlüsselt. Für jeden Kunden erstellen wir ein separates S3-Bucket-Unterverzeichnis, auf das nur mit den Anmeldedaten dieses Kunden und denen unserer internen Systembenutzer zugegriffen werden kann.

Informationen zum Hinzufügen der PGP-Verschlüsselung zu Ihren Datendateien finden Sie unter [Datei-PGP-Verschlüsselung für eingehende Datentypen](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## Schutz von Daten durch Escaping (Maskierungszeichen)  {#escaping-data}

Beachten Sie, dass [!DNL Audience Manager] bei ausgehenden Daten keine Maskierungszeichen verwendet, um sie gegen ein mögliches Cross-Site-Scripting (XSS) usw. zu schützen. Es liegt in der Verantwortung des Client, eingehenden Daten mit Maskierungszeichen zu versehen.

## HTTP Strict-Transport-Security {#hsts}

[!DNL HTTP Strict-Transport-Security (HSTS)] ist ein branchenweiter Internet-Sicherheitsmechanismus, der sowohl vor Cookie-Hijacking als auch vor Protokoll-Downgrade-Attacken schützen soll.

Die Richtlinie weist den Webbrowser an, dass nach einem sicheren [!DNL HTTPS]-Aufruf an eine bestimmte Domäne keine weiteren unsicheren Aufrufe ([!DNL HTTP]) an diese Domäne mehr zugelassen werden sollten. Dies schützt vor Man-in-the-Middle-Angriffen, bei denen ein Angreifer versuchen könnte, [!DNL HTTPS]Aufrufe auf nicht gesicherte [!DNL HTTP]-Aufrufe herunterzustufen.

Diese Richtlinie verbessert die Datensicherheit zwischen Clients und Adobe [Edge](../../reference/system-components/components-edge.md)-Servern.

### Beispiel {#hsts-example}

Angenommen, die Domäne `yourcompany.demdex.com` sendet Traffic über [!DNL HTTP] an [!DNL DCS]. [!DNL HSTS] aktualisiert die Aufrufe, um stattdessen [!DNL HTTPS] zu verwenden. Alle nachfolgenden [!DNL DCS]-Aufrufe, die von `yourcompany.demdex.com` kommen, verwenden dann [!DNL HTTPS] anstelle von [!DNL HTTP].

Weitere Informationen zu HSTS finden Sie unter [HTTP Strict Transport Security – Wikipedia](https://de.wikipedia.org/wiki/HTTP_Strict_Transport_Security).
