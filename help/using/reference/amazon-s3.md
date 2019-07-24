---
description: Informationen über Amazon Simple Storage Service (Amazon S 3).
seo-description: Informationen über Amazon Simple Storage Service (Amazon S 3).
seo-title: Amazon S 3 Info
solution: Audience Manager
title: Amazon S 3 Info
uuid: 8197 ecdf-df 8 f -488 d-bbc 0-d 8 d 4205 b 42 b 4
translation-type: tm+mt
source-git-commit: 212ec8641068a9ed4c620987bb18586ee8c7d519

---


# Amazon S3: About{#amazon-s-about}

Informationen über Amazon Simple Storage Service (Amazon S 3).

Wir empfehlen, die Verwendung von Amazon S 3 anstelle von FTP als Methode zum Abrufen von Dateien und Bereitstellen von Dateien für Partner zu empfehlen. Amazon S 3 bietet eine einfache Oberfläche für Webdienste, mit der jede beliebige Datenmenge jederzeit und jederzeit im Internet gespeichert und abgerufen werden kann.

Die Verwendung von Amazon S 3 bietet folgende Vorteile:

* **Skalierbarkeit:** Amazon S 3 bietet nahezu grenzenlose Skalierbarkeit.
* **Zuverlässigkeit und Verfügbarkeit:** Amazon S 3 bietet hohe Haltbarkeit und hohe Verfügbarkeit von Speicherdiensten.
* **Geschwindigkeit:** Amazon S 3 ermöglicht schnelle Datenübertragungen.
* **Benutzerfreundlichkeit:** Amazon S 3 ist sehr einfach zu verwenden und zu implementieren. Ihre Implementierung kann in etwa einer Stunde ausgeführt werden. Die Implementierung eines FTP-Ordners dauert viel länger.
* **Mehrteilige Uploads:** Große Dateien können schnell und effizient als mehrteilige Datei hochgeladen werden.
* **Sicherheit:** Amazon S 3 bietet eine starke Sicherheit.

   * Alle Ordner können nur für den entsprechenden Kunden oder Client aufgerufen werden.
   * HTTPS-Protokollunterstützung für Uploads und Downloads. You should always use HTTPS when transferring files in [!DNL Audience Manager].
   * Amazon S3 provides encryption-at-rest for encrypting [outbound data files](../integration/receiving-audience-data/batch-outbound-transfers/outbound-file-name-contents.md). We use the [SSE-S3](https://docs.aws.amazon.com/AmazonS3/latest/dev/serv-side-encryption.html) encryption method, which allows encryption keys to be automatically generated and managed by Amazon S3.

* **Support für Debug und Backup:** Mit Amazon S 3 können [!DNL Audience Manager] Sie exakte Kopien von Dateien beibehalten, um das Debugging oder die Wiedergabe zu vereinfachen.

Weitere Informationen zu Amazon S 3 finden Sie in den folgenden Ressourcen:

[Amazon Simple Storage Service (Amazon S 3)](https://aws.amazon.com/s3/) auf der Amazon Web Services-Website.

[Erste Schritte mit Amazon Simple Storage Service](https://docs.aws.amazon.com/AmazonS3/latest/gsg/GetStartedWithS3.html) auf der Website der AWS-Dokumentation.
