---
description: Optional können Sie Datendateien komprimieren, wenn Sie sie an den Audience Manager senden.
seo-description: As an option, you can compress data files when sending them to Audience Manager.
seo-title: File Compression for Inbound Data Transfer Files
solution: Audience Manager
title: Dateikomprimierung für eingehende Datenübertragungsdateien
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
feature: Inbound Data Transfers
exl-id: 9b3e3bef-2c93-4801-8f4f-04d9d42fd952
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 0%

---

# Dateikomprimierung für eingehende Datenübertragungsdateien{#file-compression-for-inbound-data-transfer-files}

Datendateien können beim Senden an den Audience Manager komprimiert werden.

<!-- inbound-file-compression.xml -->

Audience Manager unterstützt die GZIP-Komprimierung (`.gz`) für eingehende, asynchrone Datenübertragungen.

Audience Manager unterstützt auch unkomprimierte Dateien.

>[!IMPORTANT]
>
>Verschlüsselung von eingehenden Dateien, die mit gzip (`.gz`) komprimiert wurden, wird nicht unterstützt.
>
>Um eingehende Dateien zu verschlüsseln und zu komprimieren, verwenden Sie [PGP-Verschlüsselung](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md). [!DNL PGP] Verschlüsselung umfasst die Dateikomprimierung.

## Amazon S3-Komprimierung

Für den Versand an [!DNL Amazon S3] müssen Sie `.gz` oder unkomprimierte Dateien verwenden. Komprimierte Dateien müssen 1 GB oder kleiner sein. Wenn die Dateien größer sind, besprechen Sie den Datei- und Übertragungsprozess mit der Kundenunterstützung. Obwohl [!DNL Audience Manager] sehr große Dateien verarbeiten können, gibt es möglicherweise Möglichkeiten, die Dateigröße zu reduzieren oder die Datenübertragung effizienter zu gestalten.

>[!IMPORTANT]
>
>Ihr [!DNL FTP]-Client muss den Binärmodus verwenden, um komprimierte oder verschlüsselte Dateien zu übertragen. Komprimierte oder verschlüsselte Dateien, die im [!DNL ASCII] gesendet werden, beschädigen die Datenübertragungsdatei.

## Best Practices

* Dateien sollten [!DNL .gzip] komprimiert werden (und eine [!DNL .gz] Dateierweiterung haben).
* Die maximale komprimierte Dateigröße für eine `.gz` komprimierte Datei beträgt 1 GB.
* Optimale Split-Größen für die schnellste/früheste Verarbeitung Ihrer Dateien sind ca. 1 GB unkomprimiert oder 200-300 MB komprimiert.
* [!DNL Amazon S3] beschränkt die Dateigröße für hochgeladene Dateien auf 5 GB.
