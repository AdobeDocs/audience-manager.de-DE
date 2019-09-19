---
description: Als Option können Sie Datendateien komprimieren, wenn sie an Audience Manager gesendet werden.
seo-description: Als Option können Sie Datendateien komprimieren, wenn sie an Audience Manager gesendet werden.
seo-title: Dateikomprimierung für eingehende Datenübertragungsdateien
solution: Audience Manager
title: Dateikomprimierung für eingehende Datenübertragungsdateien
uuid: 2a68f69c-60b0-4002-863b-302d2320e356
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Dateikomprimierung für eingehende Datenübertragungsdateien{#file-compression-for-inbound-data-transfer-files}

Als Option können Sie Datendateien komprimieren, wenn sie an Audience Manager gesendet werden.

<!-- inbound-file-compression.xml -->

Audience Manager unterstützt die GZIP-Komprimierung ( `.gz`) für eingehende, asynchrone Datenübertragungen.

Audience Manager unterstützt auch nicht komprimierte Dateien.

>[!IMPORTANT]
>
>Wir unterstützen derzeit keine Verschlüsselung und Komprimierung in derselben eingehenden Datendatei. Sie können Ihre eingehenden Dateien entweder [verschlüsseln](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md) oder komprimieren.

## Amazon S3-Komprimierung

Für die Bereitstellung [!DNL Amazon S3]müssen Sie `.gz` oder nicht komprimierte Dateien verwenden. Komprimierte Dateien müssen 1 GB oder kleiner sein. Wenn die Dateien größer sind, besprechen Sie den Datei- und Übertragungsvorgang mit dem Kundendienst. Obwohl sehr große Dateien verarbeitet werden [!DNL Audience Manager] können, gibt es Möglichkeiten, die Dateigröße zu reduzieren oder die Datenübertragung effizienter zu gestalten.

>[!IMPORTANT]
>
>Ihr [!DNL FTP] Client muss den binären Modus verwenden, um komprimierte oder verschlüsselte Dateien zu übertragen. Komprimierte oder verschlüsselte Dateien, die im [!DNL ASCII] Modus gesendet werden, beschädigen die Datenübertragungsdatei.

## Best Practices

* Dateien sollten [!DNL .gzip] komprimiert werden (und eine [!DNL .gz] Dateierweiterung aufweisen).
* Die maximale komprimierte Dateigröße für eine `.gz` komprimierte Datei beträgt 1 GB.
* Optimale Aufteilung für die schnellste/schnellste Verarbeitung Ihrer Dateien ist etwa 1 GB unkomprimiert oder 200-300 MB komprimiert.
* [!DNL Amazon S3] legt für hochgeladene Dateien eine eigene maximale Dateigröße von 5 GB fest.