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

# Amazon S3: Info{#amazon-s-about}

Informationen zum Amazon Simple Storage Service (Amazon S3).

Als Best Practice wird empfohlen, Amazon S3 anstelle von FTP zu verwenden, um Dateien von abzurufen und an Partner zu übermitteln. Amazon S3 bietet eine einfache Web-Services-Oberfläche, mit der jederzeit und von überall aus Daten gespeichert und abgerufen werden können.

Zu den Vorteilen der Verwendung von Amazon S3 zählen:

* **Skalierbarkeit:** Amazon S3 bietet nahezu grenzenlose Skalierbarkeit.
* **Zuverlässigkeit und Verfügbarkeit:** Amazon S3 bietet hohe Beständigkeit und hochverfügbare Speicherdienste.
* **Geschwindigkeit:** Amazon S3 ermöglicht schnelle Datenübertragungen.
* **Benutzerfreundlichkeit:** Amazon S3 ist sehr einfach zu verwenden und zu implementieren. Ihre Implementierung kann in etwa einer Stunde ausgeführt werden. Die Implementierung eines FTP-Verzeichnisses dauert viel länger.
* **Mehrteilige Uploads:** Große Dateien können schnell und effizient hochgeladen werden, wenn sie mehrteilige Dateien hochladen.
* **Sicherheit:** Amazon S3 bietet hohe Sicherheit.

   * Alle Ordner sind nur für den entsprechenden Kunden oder Client verfügbar.
   * Unterstützung des HTTPS-Protokolls für Uploads und Downloads. Sie sollten beim Übertragen von Dateien in [!DNL Audience Manager] immer HTTPS verwenden.
   * Amazon S3 bietet eine Verschlüsselung zur Ruhezeit zum Verschlüsseln von [ausgehenden Datendateien](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). Wir verwenden die Verschlüsselungsmethode [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) , mit der Verschlüsselungsschlüssel automatisch von Amazon S3 generiert und verwaltet werden können.

* **Debug- und Backup-Unterstützung:** Amazon S3 ermöglicht es [!DNL Audience Manager], exakte Kopien von Dateien beizubehalten, um Debugging- oder Neuübertragungen zu vereinfachen.

Weitere Informationen zu Amazon S3 finden Sie in den folgenden Ressourcen:

[Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/) auf der Amazon Web Services-Website.

[Erste Schritte mit dem Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) auf der AWS-Dokumentations-Website.
