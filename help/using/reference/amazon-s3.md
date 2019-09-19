---
description: Informationen zum Amazon Simple Storage Service (Amazon S3).
seo-description: Informationen zum Amazon Simple Storage Service (Amazon S3).
seo-title: Amazon S3 Info
solution: Audience Manager
title: Amazon S3 Info
uuid: 8197ecdf-df8f-488d-bbc0-d8d4205b42b4
translation-type: tm+mt
source-git-commit: 212ec8641068a9ed4c620987bb18586ee8c7d519

---


# Amazon S3: Info{#amazon-s-about}

Informationen zum Amazon Simple Storage Service (Amazon S3).

Als bewährte Methode empfehlen wir die Verwendung von Amazon S3 anstelle von FTP als Methode zum Abrufen von Dateien und zum Senden von Dateien an Partner. Amazon S3 bietet eine einfache Web-Services-Schnittstelle, mit der Daten jederzeit und von jedem beliebigen Ort im Web gespeichert und abgerufen werden können.

Die Vorteile der Verwendung von Amazon S3 umfassen:

* **** Skalierbarkeit: Amazon S3 bietet eine nahezu grenzenlose Skalierbarkeit.
* **** Zuverlässigkeit und Verfügbarkeit: Amazon S3 bietet Speicherdienste mit hoher Haltbarkeit und hoher Verfügbarkeit.
* **** Geschwindigkeit: Amazon S3 ermöglicht eine schnelle Datenübertragung.
* **** Benutzerfreundlichkeit: Amazon S3 ist sehr einfach zu verwenden und zu implementieren. Ihre Implementierung kann in etwa einer Stunde ausgeführt werden. Die Implementierung eines FTP-Ordners dauert viel länger.
* **** Mehrteilige Uploads: Große Dateien können schnell und effizient hochgeladen werden, wenn sie mehrteilig hochgeladen werden.
* **** Sicherheit: Amazon S3 bietet hohe Sicherheit.

   * Alle Ordner sind nur für den jeweiligen Kunden oder Kunden zugänglich.
   * Unterstützung des HTTPS-Protokolls für Uploads und Downloads. Sie sollten beim Übertragen von Dateien immer HTTPS verwenden [!DNL Audience Manager].
   * Amazon S3 bietet Verschlüsselung im Ruhezustand zum Verschlüsseln [ausgehender Datendateien](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). Wir verwenden die Verschlüsselungsmethode [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) , die die automatische Erzeugung und Verwaltung von Verschlüsselungsschlüsseln durch Amazon S3 ermöglicht.

* **** Debug- und Backup-Unterstützung: Mit Amazon S3 können Sie exakte Kopien von Dateien speichern, um das Debugging oder die erneute Übertragung zu erleichtern. [!DNL Audience Manager]

Weitere Informationen zu Amazon S3 finden Sie in den folgenden Ressourcen:

[Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/) auf der Amazon Web Services-Website.

[Erste Schritte mit dem Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) auf der AWS-Dokumentation-Website.
