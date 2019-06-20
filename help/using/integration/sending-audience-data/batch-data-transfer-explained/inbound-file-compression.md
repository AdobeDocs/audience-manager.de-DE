---
description: Als Option können Sie Datendateien komprimieren, wenn Sie sie an Audience Manager senden.
seo-description: Als Option können Sie Datendateien komprimieren, wenn Sie sie an Audience Manager senden.
seo-title: Dateikomprimierung für Dateien mit Inbound-Datenübertragung
solution: Audience Manager
title: Dateikomprimierung für Dateien mit Inbound-Datenübertragung
uuid: 2 a 68 f 69 c -60 b 0-4002-863 b -302 d 2320 e 356
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Dateikomprimierung für Dateien mit Inbound-Datenübertragung{#file-compression-for-inbound-data-transfer-files}

Als Option können Sie Datendateien komprimieren, wenn Sie sie an Audience Manager senden.

<!-- inbound-file-compression.xml -->

Audience Manager unterstützt die GZIP ( `.gz`)-Komprimierung für eingehende, asynchrone Datenübertragungen.

Audience Manager unterstützt auch nicht komprimierte Dateien.

>[!IMPORTANT]
>
>Verschlüsselung und Komprimierung werden derzeit nicht in derselben Inbound-Datendatei unterstützt. Sie können Ihre eingehenden Dateien [entweder verschlüsseln oder](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md) komprimieren.

## Komprimierung bei Amazon S 3

Für die Bereitstellung [!DNL Amazon S3]müssen Sie Dateien verwenden `.gz` oder nicht komprimierte Dateien. Komprimierte Dateien müssen 1 GB oder kleiner sein. Wenn die Dateien größer sind, besprechen Sie die Datei und übertragen Sie sie mit der Kundenunterstützung. Auch wenn [!DNL Audience Manager] sehr große Dateien verarbeitet werden können, kann es Wege geben, die Dateigröße zu verringern oder die Datenübertragung effizienter zu gestalten.

>[!IMPORTANT]
>
>Ihr [!DNL FTP] Client muss den binären Modus verwenden, um komprimierte oder verschlüsselte Dateien zu übertragen. Komprimierte oder verschlüsselte Dateien, die im Modus [!DNL ASCII] gesendet werden, verfälschen die Datenübertragungsdatei.

## Best Practices

* Dateien sollten [!DNL .gzip] komprimiert werden (und haben eine [!DNL .gz] Dateierweiterung).
* Die maximale komprimierte Dateigröße für eine `.gz` komprimierte Datei beträgt 1 GB.
* Optimale Größengrößen für die schnellste/früheste Verarbeitung Ihrer Dateien beträgt etwa 1 GB unkomprimiert oder 200 bis 300 MB komprimiert.
* [!DNL Amazon S3] hat eine eigene Beschränkung von 5 GB für hochgeladene Dateien.