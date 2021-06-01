---
description: Dateiübertragungs-Kontrolldateien (.info) bieten Metadateninformationen zu Dateiübertragungen, sodass Partner überprüfen können, ob der Audience Manager die Dateiübertragungen ordnungsgemäß verarbeitet hat.
seo-description: Dateiübertragungs-Kontrolldateien (.info) bieten Metadateninformationen zu Dateiübertragungen, sodass Partner überprüfen können, ob der Audience Manager die Dateiübertragungen ordnungsgemäß verarbeitet hat.
seo-title: Übertragungssteuerungsdateien für Protokolldateiübertragungen
solution: Audience Manager
title: Übertragungssteuerungsdateien für Protokolldateiübertragungen
uuid: ef58213e-7b37-4c5a-8556-0de695706793
feature: Ausgehende Datenübertragungen
exl-id: 4fd1aab1-2dc2-4de9-97be-58e79825db40
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 6%

---

# Übertragungssteuerungsdateien für Protokolldateiübertragungen {#transfer-control-files-for-log-file-transfers}

Dateiübertragungs-Kontrolldateien ([!DNL .info]) bieten Metadateninformationen über Dateiübertragungen, sodass Partner überprüfen können, ob der Audience Manager die Dateiübertragungen ordnungsgemäß verarbeitet hat.

[!DNL Audience Manager] sendet bei jeder Dateiübertragung eine Übertragungssteuerungsdatei an einen Partner. Aufgrund der Multi-Thread-Natur des [!DNL FTP]-Herausgebers kann die Übertragungssteuerungsdatei gesendet werden, bevor die eigentlichen Dateien übertragen werden.

Die Metadaten in der Datei [!DNL .info] ermöglichen Partnern Folgendes:

* Bestimmen Sie, wann ein vollständiger Übertragungszyklus abgeschlossen ist (die Gesamtzahl der Dateien in der Sequenz wurde bereitgestellt).
* Bestimmen Sie, ob eine beliebige Datei in der Sequenz vollständig/korrekt ist (indem Sie die Größe der Datei in Byte und die Gesamtanzahl der Zeilen überprüfen).
* Beim Überprüfen der Anzahl der Zeilen in den Rohdateien wird die Anzahl der Zeilen nach dem Laden der Dateien in die Datenbank am Empfangs-Ende (Dateigröße in Zeilen) vernachlässigt.

## Namenskonventionen für Dateien {#file-naming-conventions}

Die Übertragungssteuerungsdatei hat denselben Namen wie der Stamm des Batches/der Sequenz mit der Dateierweiterung [!DNL .info] .

Wenn beispielsweise die erste Datei in der Sequenz den Namen hatte: [!DNL ftp_12345_67890_full_1500727351632-1.sync] würde die Kontrolldatei [!DNL ftp_12345_67890_iter_1500727351632.info] heißen.

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
> Die Batch-Gesamtzahlen schließen die [!DNL .info]-Datei selbst aus. Das heißt, die Summen enthalten nicht die Datei [!DNL .info], ihre Byte-Größe oder die Zeilenanzahl.
>
> Byte-Größen von Dateien und Zeilenanzahl enthalten alle Header- und (leeren) Abstand-Zeilen/Zeilen. Um die Anzahl der tatsächlichen Datenzeilen/Zeilen zu erhalten, subtrahieren Sie Kopfzeilen.
>
> Die Gesamtzeilen in Batch- und Gesamt-Byte-Größe beinhalten alle Header- und Leerzeichenzeilen.
