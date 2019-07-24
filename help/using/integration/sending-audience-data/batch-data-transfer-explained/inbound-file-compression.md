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


# File Compression for Inbound Data Transfer Files{#file-compression-for-inbound-data-transfer-files}

Als Option können Sie Datendateien komprimieren, wenn Sie sie an Audience Manager senden.

<!-- inbound-file-compression.xml -->

Audience Manager supports gzip ( `.gz`) compression for inbound, asynchronous data transfers.

Audience Manager unterstützt auch nicht komprimierte Dateien.

>[!IMPORTANT]
>
>Verschlüsselung und Komprimierung werden derzeit nicht in derselben Inbound-Datendatei unterstützt. You can select to either [encrypt](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-encryption.md) or compress your inbound files.

## Komprimierung bei Amazon S 3

For delivery to [!DNL Amazon S3], you must use `.gz` or uncompressed files. Komprimierte Dateien müssen 1 GB oder kleiner sein. Wenn die Dateien größer sind, besprechen Sie die Datei und übertragen Sie sie mit der Kundenunterstützung. Although [!DNL Audience Manager] can handle very large files, there may be ways to reduce the file size or make transfer of data more efficient.

>[!IMPORTANT]
>
>Your [!DNL FTP] client must use binary mode to transfer compressed or encrypted files. Compressed or encrypted files sent in [!DNL ASCII] mode will corrupt the data transfer file.

## Best Practices

* Files should be [!DNL .gzip] compressed (and have a [!DNL .gz] file extension.)
* The maximum compressed file size for a `.gz` compressed file is 1 GB.
* Optimale Größengrößen für die schnellste/früheste Verarbeitung Ihrer Dateien beträgt etwa 1 GB unkomprimiert oder 200 bis 300 MB komprimiert.
* [!DNL Amazon S3] hat eine eigene Beschränkung von 5 GB für hochgeladene Dateien.