---
description: Als Option können Sie Datendateien komprimieren, wenn sie an Audience Manager gesendet werden.
seo-description: Als Option können Sie Datendateien komprimieren, wenn sie an Audience Manager gesendet werden.
seo-title: Dateikomprimierung für eingehende Datenübertragungsdateien
solution: Audience Manager
title: Dateikomprimierung für eingehende Datenübertragungsdateien
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 10%

---


# Dateikomprimierung für eingehende Datenübertragungsdateien{#file-compression-for-inbound-data-transfer-files}

Sie können Datendateien komprimieren, wenn Sie sie an Audience Manager senden.

<!-- inbound-file-compression.xml -->

Audience Manager unterstützt die gzip-Komprimierung (`.gz`) für eingehende, asynchrone Datenübertragungen.

Audience Manager unterstützt auch nicht komprimierte Dateien.

>[!IMPORTANT]
>
>Wir unterstützen keine Verschlüsselung für eingehende Dateien, die mit gzip komprimiert werden (`.gz`).
>
>Verwenden Sie zum Verschlüsseln und Komprimieren von eingehenden Dateien [PGP-Verschlüsselung](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). [!DNL PGP] Verschlüsselung beinhaltet Dateikomprimierung.

## Amazon S3-Komprimierung

Zum Versand von [!DNL Amazon S3] müssen Sie `.gz`- oder nicht komprimierte Dateien verwenden. Komprimierte Dateien müssen 1 GB oder kleiner sein. Wenn die Dateien größer sind, besprechen Sie den Datei- und Übertragungsvorgang mit dem Kundendienst. Obwohl [!DNL Audience Manager] sehr große Dateien verarbeiten kann, gibt es Möglichkeiten, die Dateigröße zu reduzieren oder die Datenübertragung effizienter zu gestalten.

>[!IMPORTANT]
>
>Ihr [!DNL FTP]-Client muss den binären Modus verwenden, um komprimierte oder verschlüsselte Dateien zu übertragen. Komprimierte oder verschlüsselte Dateien, die im [!DNL ASCII]-Modus gesendet werden, beschädigen die Datenübertragungsdatei.

## Best Practices

* Dateien müssen komprimiert ([!DNL .gzip]) sein (und eine [!DNL .gz] Dateierweiterung aufweisen).
* Die maximale komprimierte Dateigröße für eine `.gz`-komprimierte Datei beträgt 1 GB.
* Optimale Aufteilung für die schnellste/schnellste Verarbeitung Ihrer Dateien ist ca. 1 GB unkomprimiert oder 200-300 MB komprimiert.
* [!DNL Amazon S3] legt für hochgeladene Dateien eine eigene maximale Dateigröße von 5 GB fest.
