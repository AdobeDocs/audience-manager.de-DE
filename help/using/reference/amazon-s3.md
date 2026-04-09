---
description: Informationen zum Amazon Simple Storage Service (Amazon S3).
seo-description: Information about Amazon Simple Storage Service (Amazon S3).
seo-title: Amazon S3  About
solution: Audience Manager
title: Amazon S3 Info
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: Reference
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
TQID: https://experienceleague.adobe.com/HRLp9cXzF3yRFulThePWxGt6TRD1HxgecSiFlnSAxlA
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: a8b0238e-1d43-4679-a3b4-5ba1bad83baa
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 269
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
   * Amazon S3 bietet Verschlüsselung im Ruhezustand zum Verschlüsseln ([&#x200B; Datendateien](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). Wir verwenden die [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) Verschlüsselungsmethode, mit der Verschlüsselungsschlüssel automatisch von Amazon S3 generiert und verwaltet werden können.

* **Debug- und Backup-Unterstützung:** Mit Amazon S3 können [!DNL Audience Manager] exakte Dateikopien beibehalten, um das Debugging oder die erneute Übertragung zu vereinfachen.

Weitere Informationen zu Amazon S3 finden Sie in den folgenden Ressourcen:

[Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/) auf der Amazon Web Services-Website.

[Erste Schritte mit dem Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) auf der AWS-Dokumentations-Website.
