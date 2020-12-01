---
description: Transfer-Control-Dateien (.info) bieten Metadateninformationen zu Dateiübertragungen, damit die Partner überprüfen können, ob die Dateiübertragungen von Audience Manager korrekt verarbeitet wurden.
seo-description: Transfer-Control-Dateien (.info) bieten Metadateninformationen zu Dateiübertragungen, damit die Partner überprüfen können, ob die Dateiübertragungen von Audience Manager korrekt verarbeitet wurden.
seo-title: Übertragungssteuerungsdateien für Protokolldateiübertragungen
solution: Audience Manager
title: Übertragungssteuerungsdateien für Protokolldateiübertragungen
uuid: ef58213e-7b37-4c5a-8556-0de695706793
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: 033057e080a72c82ec8ff9233e199d5e204a622c
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 6%

---


# Übertragungssteuerungsdateien für Protokolldateiübertragungen {#transfer-control-files-for-log-file-transfers}

Übertragungssteuerungsdateien ([!DNL .info]) bieten Metadateninformationen zu Dateiübertragungen, damit die Partner überprüfen können, ob die Dateiübertragungen von Audience Manager korrekt verarbeitet wurden.

[!DNL Audience Manager] sendet bei jeder Dateiübertragung eine Transfersteuerungsdatei an einen Partner. Aufgrund der Multi-Thread-Charakteristik des [!DNL FTP]-Herausgebers kann die Übertragungssteuerungsdatei gesendet werden, bevor die eigentlichen Dateien übertragen werden.

Die Metadaten in der Datei [!DNL .info] ermöglichen Partnern Folgendes:

* Bestimmen Sie, wann ein vollständiger Übertragungszyklus abgeschlossen ist (die Gesamtzahl der in der Sequenz enthaltenen Dateien wurde bereitgestellt).
* Bestimmen Sie, ob eine beliebige Datei in der Sequenz vollständig/korrekt ist (durch Untersuchung der Größe der Datei in Byte und der Gesamtanzahl der Zeilen).
* Bei der Überprüfung der Anzahl der Zeilen in Rohdateien wird die Anzahl der Zeilen nach dem Laden der Dateien in die Datenbank am Empfängerende (Dateigröße in Zeilen) zurückgesetzt.

## Dateibenennungskonventionen {#file-naming-conventions}

Die Datei für die Übertragungssteuerung hat denselben Namen wie der Stammordner des Stapels/der Sequenz mit einer [!DNL .info] Dateierweiterung.s

Wenn die erste Datei in der Sequenz beispielsweise den Namen hatte: [!DNL ftp_12345_67890_full_1500727351632-1.sync] würde die Steuerelementdatei [!DNL ftp_12345_67890_iter_1500727351632.info] heißen.

## Dateiformat {#file-format}

```
{
  Files: [
    {
      FileByteSize: 293029329,
      FileLineCount: 36893908,
      FileName: "ftp_12345_67890_full_1500727351632-1.sync.gz",
      FileSequenceNumber: 1,
      md5: "983g634be2ad5263c6a6c4958bf61d9f"
    },
    {
      FileByteSize: 293039238,
      FileLineCount: 36895184,
      FileName: "ftp_12345_67890_full_1500727351632-2.sync.gz",
      FileSequenceNumber: 2,
      md5: "6sn9907c8e78cfd78409622e7b55a984"
    },
    {
      FileByteSize: 293050833,
      FileLineCount: 36896787,
      FileName: "ftp_12345_67890_full_1500727351632-3.sync.gz",
      FileSequenceNumber: 3,
      md5: "7cdfb8e74cd6cec1jy6vel21ccb4a962"
    },
    {
      FileByteSize: 218425764,
      FileLineCount: 27498226,
      FileName: "ftp_12345_67890_full_1500727351632-4.sync.gz",
      FileSequenceNumber: 4,
      md5: "7hs53149f8a2444457g968f04cbbdee5"
    }
  ],
  Totals: {
    FileName: "ftp_12345_67890_full_1500727351632.sync",
    TotalByteSize: 1097545164,
    TotalNumberFiles: 4,
    TotalNumberLines: 138184105
    }
}
```

>[!NOTE]
>
> Die Gesamtzahl der Stapel ist nicht in der Datei [!DNL .info] enthalten. Das heißt, die Summen enthalten nicht die Datei [!DNL .info], ihre Bytegröße oder ihre Zeilenzahl.
>
> Die Bytegrößen von Dateien und Zeilenzahlen beinhalten alle Header- und Platzhalterlinien/Zeilen (leer). Um die Anzahl der tatsächlichen Datenzeilen/Zeilen abzurufen, ziehen Sie die Kopfzeilen ab.
>
> Zeilen insgesamt im Stapel und Bytegröße insgesamt schließen Kopf- und Leerzeichenzeilen ein.