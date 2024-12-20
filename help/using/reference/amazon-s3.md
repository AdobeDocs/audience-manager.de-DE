---
description: Informationen zum Amazon Simple Storage Service (Amazon S3).
seo-description: Information about Amazon Simple Storage Service (Amazon S3).
seo-title: Amazon S3  About
solution: Audience Manager
title: Amazon S3 Info
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: Reference
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---

# Amazon S3: Wissenswertes{#amazon-s-about}

Informationen zum Amazon Simple Storage Service (Amazon S3).

Als Best Practice empfehlen wir die Verwendung von Amazon S3 anstelle von FTP als Methode zum Abrufen von Dateien von und zum Bereitstellen von Dateien für Partner. Amazon S3 bietet eine einfache Web-Services-Schnittstelle, über die Daten jeder beliebigen Menge jederzeit und von jedem beliebigen Ort im Web gespeichert und abgerufen werden können.

Die Verwendung von Amazon S3 bietet folgende Vorteile:

* **Skalierbarkeit:** Amazon S3 bietet nahezu unbegrenzte Skalierbarkeit.
* **Zuverlässigkeit und Verfügbarkeit:** Amazon S3 bietet hohe Haltbarkeit und Hochverfügbarkeits-Speicherservices.
* **Geschwindigkeit:** Amazon S3 ermöglicht schnelle Datenübertragungen.
* **Benutzerfreundlichkeit:** Amazon S3 ist sehr einfach zu bedienen und zu implementieren. Ihre Implementierung kann in etwa einer Stunde ausgeführt werden. Die Implementierung eines FTP-Verzeichnisses dauert viel länger.
* **Mehrteilige Uploads:** Große Dateien können schnell und effizient als mehrteilige Datei-Uploads hochgeladen werden.
* **Sicherheit:** Amazon S3 bietet hohe Sicherheit.

   * Alle Verzeichnisse sind nur für den entsprechenden Kunden oder Client zugänglich.
   * Unterstützung des HTTPS-Protokolls für Uploads und Downloads. Beim Übertragen von Dateien in [!DNL Audience Manager] sollten Sie immer HTTPS verwenden.
   * Amazon S3 bietet Verschlüsselung im Ruhezustand zum Verschlüsseln ([ Datendateien](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). Wir verwenden die [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) Verschlüsselungsmethode, mit der Verschlüsselungsschlüssel automatisch von Amazon S3 generiert und verwaltet werden können.

* **Debug- und Backup-Unterstützung:** Mit Amazon S3 können [!DNL Audience Manager] exakte Dateikopien beibehalten, um das Debugging oder die erneute Übertragung zu vereinfachen.

Weitere Informationen zu Amazon S3 finden Sie in den folgenden Ressourcen:

[Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/) auf der Amazon Web Services-Website.

[Erste Schritte mit dem Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) auf der AWS-Dokumentations-Website.
