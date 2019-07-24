---
description: Der Audience Manager nimmt Datensicherheit und Datenschutz sehr ernst. Wir arbeiten daran, unsere Systeme sicher zu halten und Ihre wertvollen Daten zu schützen.
seo-description: Der Audience Manager nimmt Datensicherheit und Datenschutz sehr ernst. Wir arbeiten daran, unsere Systeme sicher zu halten und Ihre wertvollen Daten zu schützen.
seo-title: Datensicherheit
solution: Audience Manager
title: Datensicherheit
uuid: 33 ad 19 ca -4690-4 d 97-853 b -1882 d 7 d 4 ac 01
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Data Security {#data-security}

Der Audience Manager nimmt Datensicherheit und Datenschutz sehr ernst. Wir arbeiten daran, unsere Systeme sicher zu halten und Ihre wertvollen Daten zu schützen.

Zu den Sicherheitspraktiken von Audience Manager zählen externe und interne Prüfungen, Aktivitätsprotokollierung, Schulungen und andere Verfahren, mit denen Sie unsere Systeme und wertvolle Daten schützen können. Wir sind überzeugt, dass ein sicheres Produkt dabei hilft, die Vertrauenskunden zu erstellen und zu erhalten.

In Audience Manager betrachten wir die Sicherheit in drei Hauptkategorien:

| Sicherheitstyp | Bietet Unterstützung für |
|---|---|
| **Informationssicherheit** | Authentifizierung, Verschlüsselung und Datenspeicherung auf Unternehmensebene |
| **Datenverlust/Transparenz** | Tiefgründige und umsetzbare Einblicke in Aktivitäten auf der Site, die zu Datenverlust beitragen oder diese ausmachen |
| **Prozess-/Richtlinienverbesserungen** | Kunden, die mit bewährten Verfahren für Datenschutz und Datensicherheit arbeiten |

## Systems, Training, and Access {#systems-training-access}

Prozesse, mit denen unser System und Ihre Daten geschützt werden.

**Externe Sicherheitsprüfung:** Audience Manager testet die Sicherheit auf Jahr und Quartal.

* Jährlich: Ein Jahr lang führt Audience Manager einen vollständigen Test zur Penetration durch, der von einem unabhängigen Drittanbieterunternehmen ausgeführt wird. Der Test soll Sicherheitslücken in der Anwendung identifizieren. Die Tests umfassen Scannen von Cross-Site-Skripten, SQL-Injektionen, Formularparametermanipulation und anderen Sicherheitslücken auf Anwendungsebene.
* Vierteljährlich: Einmal pro Quartal prüfen interne Teams Sicherheitslücken. Zu diesen Tests zählen Netzwerk-Scans für offene Ports und Sicherheitslücken.

**Systemsicherheit:** So bewahren Sie den Datenschutz und die private Sicherheit mit Audience Manager auf:

* Blockiert Anforderungen von nicht autorisierten IP-Adressen.
* Schützt Daten hinter Firewalls, vpns und dem virtuellen privaten Cloud-Speicher.
* Verfolgt Änderungen in den Kunden- und Steuerungsdatenbanken mit der auslöserbasierten Prüfprotokollierung. Diese Protokolle verfolgen alle Änderungen auf Datenbankebene, einschließlich der Benutzer-ID und IP-Adresse, aus der Änderungen vorgenommen werden.

**Sicherheitselemente:** Audience Manager verfügt über ein dediziertes Netzwerkbetriebsteam, das Firewalls und Geräte für die Erkennungserkennung überwacht. Nur wichtige Mitarbeiter haben Zugriff auf unsere Sicherheitstechnologie und Ihre Daten.

**Sicherheitschulung:** Intern erstreckt sich unser Sicherheitsengagement auf Entwickler, die an unserem Produkt arbeiten. Adobe bietet eine formelle Schulung für Entwickler zum Erstellen sicherer Anwendungen und Dienste.

**Sicherer Zugriff:** Audience Manager erfordert sichere Passwörter für die Anmeldung beim System. See [password requirements](../../reference/password-requirements.md).

## Privacy and Personally Identifiable Information (PII) {#pii}

Prozesse, mit denen persönliche Informationen sicher bleiben. For additional privacy information, see the [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html).

**PII-Daten:** Audience Manager verbietet Kunden und Datenpartnern vertraglich das Senden von PII-Informationen an unser System. Darüber hinaus enthält die Unique User ID (UUID) PII-Daten nicht als Teil des ID-Generierungsalgorithmus.

**IP-Adressen:** Audience Manager erfasst IP-Adressen. IP-Adressen werden in Datenverarbeitung und Protokollierungsprozessen verwendet. Sie sind außerdem für geografische/Standortbasierte Suchen und Targeting erforderlich. Außerdem werden alle IP-Adressen innerhalb von beibehaltenen Protokolldateien innerhalb von 90 Tagen verschleiert.

## Data Partitioning {#data-partitioning}

Prozesse, die den Schutz von Daten einzelner Kunden unterstützen.

**Eigenschaftspartitionpartition:** Ihre Daten (Eigenschaften, IDs usw.) wird vom Client partiiert. Dies verhindert eine unbeabsichtigte Informationsexposition zwischen verschiedenen Clients. Eigenschaftsdaten in Cookies werden beispielsweise vom Kunden partiiert und in einer client-spezifischen Subdomäne gespeichert. Sie kann nicht versehentlich von einem anderen Audience Manager-Client gelesen oder verwendet werden. Furthermore, trait data stored in the [!UICONTROL Profile Cache Servers (PCS)] is also partitioned by customer. Dadurch wird verhindert, dass andere Kunden versehentlich Ihre Daten in einem Ereignisaufruf oder einer anderen Anforderung verwenden.

**Datenpartitionen in Berichten:** Client-IDs sind Teil des Identifikationsschlüssels in allen Berichterstellungstabellen, und Berichtabfragen werden nach ID gefiltert. Dadurch wird verhindert, dass Ihre Daten in den Berichten eines anderen Audience Manager-Kunden erscheinen.

## Inbound Server-to-Server (S2S) Transfers {#inbound-s2s}

Adobe Audience Manager unterstützt zwei Hauptmethoden zum Übertragen von S 2 S-Datendateien an unsere Systeme:

Beide Methoden sind für die Sicherheit unserer Kunden- und Partnerdaten ausgelegt, während Daten zwischen ihren Systemen und unserem System im Flug liegen.

**SFTP:** Für die SFTP-Option wählen die meisten Kunden Dateien über das Secure FTP (SFTP)-Protokoll aus, das das Protokoll Secure Shell (SSH) verwendet. Diese Methode stellt sicher, dass Dateien während des Flugs zwischen den Systemen des Kunden und dem Adobe-System verschlüsselt werden. Für jeden Kunden erstellen wir einen Speicherort für eine javastierte Dropbox auf unseren SFTP-Servern, der an ein Benutzerkonto auf diesem System gebunden ist. Nur die berechtigten und privilegierten internen Systembenutzer des Kunden können auf diesen Speicherort für die javastierte Dropbox zugreifen. Für andere Kunden ist dieses Gefängnis nie zugänglich.

**Amazon Web Services S 3 über HTTPS:** Für die S 3-Bereitstellungsoption empfehlen wir allen Kunden, ihre S 3-Clients für die Verwendung der HTTPS-Verschlüsselungsmethode für Dateiübertragungen zu konfigurieren (dies ist nicht die Standardeinstellung, damit sie explizit konfiguriert werden muss). Die HTTPS-Option wird sowohl vom Befehlszeilenwerkzeug s 3 als auch von den S 3-Bibliotheken unterstützt, die in jeder Hauptprogrammiersprache verfügbar sind. Wenn diese HTTPS-Option aktiviert ist, werden die Daten des Kunden während des Flugstarts zu unseren Systemen verschlüsselt. Für jeden Kunden erstellen wir einen separaten S 3-Unterordner, auf den nur die Anmeldeinformationen dieses Kunden und der unserer internen Systembenutzer zugreifen können.

To add PGP encryption to your data files, see [File PGP Encryption for Inbound Data Types](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md).

## Protecting Data by Escaping {#escaping-data}

Note that [!DNL Audience Manager] does not escape outgoing data to secure it against possible cross-site scripting (XSS), etc. Es ist die Aufgabe des Clients, eingehende Daten zu Escape.
