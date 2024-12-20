---
description: Datenübertragungssteuerungsdateien (.info) liefern Metadateninformationen über Dateiübertragungen, damit Partner überprüfen können, ob der Audience Manager Dateiübertragungen korrekt verarbeitet hat.
seo-description: Transfer-control (.info) files provide metadata information about file transfers so that partners can verify that Audience Manager handled file transfers correctly.
seo-title: Transfer-Control Files for Log File Transfers
solution: Audience Manager
title: Kontrolldateien für die Übertragung von Protokolldateien
uuid: ef58213e-7b37-4c5a-8556-0de695706793
feature: Outbound Data Transfers
exl-id: 4fd1aab1-2dc2-4de9-97be-58e79825db40
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 0%

---

# Kontrolldateien für die Übertragung von Protokolldateien {#transfer-control-files-for-log-file-transfers}

[!DNL .info]-Dateien (Transfer Control) liefern Metadateninformationen zu Dateiübertragungen, damit Partner überprüfen können, ob der Audience Manager Dateiübertragungen korrekt verarbeitet hat.

[!DNL Audience Manager] sendet bei jeder Dateiübertragung eine Kontrolldatei für die Übertragung an einen Partner. Aufgrund der Multi-Thread-Natur des [!DNL FTP]-Herausgebers kann die Datei für die Übertragungssteuerung gesendet werden, bevor die eigentlichen Dateien übertragen werden.

Die Metadaten in der [!DNL .info] ermöglichen Partnern Folgendes:

* feststellen, wann ein vollständiger Übertragungszyklus abgeschlossen ist (die Gesamtzahl der Dateien in der Sequenz wurden zugestellt);
* Stellen Sie fest, ob eine Datei in der Sequenz vollständig/korrekt ist (indem Sie die Größe der Datei in Byte und die Gesamtzahl der Zeilen überprüfen).
* Überprüfen Sie die Anzahl der Zeilen in den Rohdateien im Vergleich zur Anzahl der Zeilen, nachdem die Dateien auf der empfangenden Seite in die Datenbank geladen wurden (Größe der Datei in Zeilen).

## Konventionen für die Dateibenennung {#file-naming-conventions}

Die Datei für die Übertragungssteuerung hat denselben Namen wie der Stamm des Batches bzw. der Sequenz mit der Dateierweiterung &quot;[!DNL .info]&quot;.

Wenn beispielsweise die erste Datei in der Sequenz die Bezeichnung [!DNL ftp_12345_67890_full_1500727351632-1.sync] hätte, würde die Steuerdatei [!DNL ftp_12345_67890_iter_1500727351632.info] heißen.

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
> Die Gesamtanzahl der Batches enthält nicht die [!DNL .info]. Das heißt, dass die Gesamtwerte weder die [!DNL .info]-Datei noch ihre Byte-Größe oder Zeilenanzahl enthalten.
>
> Die Byte-Größe der Dateien und die Zeilenanzahl schließen alle Kopfzeilen und Leerzeilen (leere Zeilen) ein. Um die Anzahl der tatsächlichen Datenzeilen/Zeilen abzurufen, ziehen Sie die Kopfzeilen ab.
>
> Die Gesamtzeilen im Batch und die Gesamtbyte-Größe schließen alle Kopfzeilen und Leerzeilen ein.
