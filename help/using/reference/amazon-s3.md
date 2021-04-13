---
description: Informationen zum Amazon Simple Datenspeicherung Service (Amazon S3).
seo-description: Informationen zum Amazon Simple Datenspeicherung Service (Amazon S3).
seo-title: Amazon S3 Info
solution: Audience Manager
title: Amazon S3 Info
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
feature: 'Referenz '
exl-id: 12c4f00d-2916-4224-b834-d3a9ea86314a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 1%

---

# Amazon S3: Info{#amazon-s-about}

Informationen zum Amazon Simple Datenspeicherung Service (Amazon S3).

Als bewährte Methode empfehlen wir die Verwendung von Amazon S3 anstelle von FTP als Methode zum Abrufen von Dateien und zum Senden von Dateien an Partner. Amazon S3 bietet eine einfache Web-Services-Schnittstelle, mit der Daten jederzeit und von jedem beliebigen Ort im Web gespeichert und abgerufen werden können.

Die Verwendung von Amazon S3 bietet unter anderem folgende Vorteile:

* **Skalierbarkeit:** Amazon S3 bietet eine nahezu grenzenlose Skalierbarkeit.
* **Zuverlässigkeit und Verfügbarkeit:** Amazon S3 bietet Datenspeicherung mit hoher Haltbarkeit und hoher Verfügbarkeit.
* **Geschwindigkeit:** Amazon S3 ermöglicht schnelle Datenübertragung.
* **Benutzerfreundlichkeit:** Amazon S3 ist sehr einfach zu verwenden und zu implementieren. Ihre Implementierung kann in etwa einer Stunde ausgeführt werden. Die Implementierung eines FTP-Ordners dauert viel länger.
* **Mehrteilige Uploads:** Große Dateien können beim Hochladen mehrerer Teile schnell und effizient hochgeladen werden.
* **Sicherheit:** Amazon S3 bietet hohe Sicherheit.

   * Alle Ordner sind nur für den jeweiligen Kunden oder Kunden zugänglich.
   * Unterstützung des HTTPS-Protokolls für Uploads und Downloads. Sie sollten beim Übertragen von Dateien in [!DNL Audience Manager] immer HTTPS verwenden.
   * Amazon S3 bietet Verschlüsselung bei der Speicherung zum Verschlüsseln von [ausgehenden Datendateien](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). Wir verwenden die Verschlüsselungsmethode [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html), mit der Verschlüsselungsschlüssel automatisch von Amazon S3 generiert und verwaltet werden können.

* **Debug- und Backup-Unterstützung:** Amazon S3 ermöglicht  [!DNL Audience Manager] die Beibehaltung exakter Dateikopien, um das Debugging oder erneute Transfers zu vereinfachen.

Weitere Informationen zu Amazon S3 finden Sie in den folgenden Ressourcen:

[Amazon Simple Datenspeicherung Service (Amazon S3)](https://aws.amazon.com/s3/) auf der Amazon Web Services-Website.

[Beginnen Sie mit Amazon Simple Datenspeicherung ](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) Service auf der AWS-Dokumentations-Website.
