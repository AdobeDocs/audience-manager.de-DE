---
description: Der S3-Statusordner enthält eine .info-Datei mit Erfolgs- und Fehlerinformationen zu den hochgeladenen Dateien. Die Datei enthält JSON-formatierte Daten mit Statusergebnissen in einem Array.
seo-description: Der S3-Statusordner enthält eine .info-Datei mit Erfolgs- und Fehlerinformationen zu den hochgeladenen Dateien. Die Datei enthält JSON-formatierte Daten mit Statusergebnissen in einem Array.
seo-title: Statusaktualisierungen für Metadatendateien
solution: Audience Manager
title: Statusaktualisierungen für Metadatendateien
uuid: 56a1e88a-41da-4d51-a21e-2be98cca7fa2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Statusaktualisierungen für Metadatendateien{#status-updates-for-metadata-files}

Der S3-Statusordner enthält eine `.info` Datei mit Erfolgs- und Fehlerinformationen zu den hochgeladenen Dateien. Die Datei enthält JSON-formatierte Daten mit Statusergebnissen in einem Array.

Der Inhalt Ihrer `.info` Datei sieht ähnlich aus wie in diesem Beispiel.

```js
//sample file path
/log_ingestion/pid=1234/dpid=567/status/20150827.info

//sample contents
{
    "Files": [
        {
            "FileByteSize": 488900,
            "FileChecksumMD5": "94b821082daff242e452c0d8796b08f0",
            "FileName": "20141112_4_2",
            "MetadataType": "Creative",
            "Parent": "Site",
            "Status": "SUCCESS",
            "Description": ""
        },
        {
            "FileByteSize": 58812,
            "FileChecksumMD5": "db79f148e6a635629701c13a7bcc8db0",
            "FileName": "20141112_0_4",
            "MetadataType": "Site",
            "Parent": "None",
            "Status": "FAILURE",
            "Description": "Invalid format."
        }
    ],
    "Summary": {
        "Day": "2014-11-12",
        "ProcessingTimeRFC2822": "Wed, 10 Dec 2014 21:07:58 -0000",
        "ProcessingTimestampPOSIX": 1418263678,
        "TotalByteSize": 547712,
        "TotalNumberFiles": 2,
        "NumberSuccess": 1,
        "NumberFailure": 1,
        "GlobalStatus": "FAILURE"
    }
}
```

## Definierte Schlüssel-Wert-Paare für Metadaten {#key-value-pairs}

In den folgenden Tabellen sind die Schlüssel in den Abschnitten `Files` und die Schlüssel in einer Metadaten-Statusdatei aufgelistet und definiert `Summary` .

**Tasten im Dateiarray**

<table id="table_BF23C032FEFA446282E9364E85BE8C9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Schlüssel </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Beschreibung</code> </p> </td> 
   <td colname="col2"> <p>Enthält eine kurze Beschreibung, warum die Verarbeitung fehlgeschlagen ist. Dieses Feld ist leer, wenn die Verarbeitung erfolgreich war. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Dateigröße in Byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Die MD5-Prüfsumme für die Metadatendatei, die in Ihren <code> Metadatenordner</code> hochgeladen wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>Der Name der Metadatendatei, die in Ihren <code> Metadatenordner</code> hochgeladen wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MetadataType</code> </p> </td> 
   <td colname="col2"> <p>Der lesbare Name für den Datentyp, den Ihre Datei enthält. Er basiert auf der untergeordneten ID in Ihrem Dateinamen. </p> <p>Siehe <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Benennungsregeln für Metadatendateien</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Übergeordnet</code> </p> </td> 
   <td colname="col2"> <p>Der lesbare Name für den Datentyp, den Ihre Datei enthält. Er basiert auf der übergeordneten ID in Ihrem Dateinamen. </p> <p>Siehe <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Benennungsregeln für Metadatendateien</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Status</code> </p> </td> 
   <td colname="col2"> <p>Gibt 2 Textwerte zurück, die den Verarbeitungsstatus Ihrer Metadatendatei beschreiben: </p> 
    <ul id="ul_3814EBB6B42B4EB294B1ABA5782190B6"> 
     <li id="li_92AAECE7E9A44B1193A1D93ABBCE46B0"> <code> ERFOLG</code> </li> 
     <li id="li_3109F4E254374117A89CB989F221CB18"> <code> FEHLER</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Tasten im Zusammenfassungsobjekt**

<table id="table_C765A0CDBAA14A2FB5E0D38BDD1D292A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Schlüssel </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Tag</code> </p> </td> 
   <td colname="col2"> <p>Dateiverarbeitungsdatum im <code><i>Format yyyy-mm-dd</i></code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> GlobalStatus</code> </p> </td> 
   <td colname="col2"> <p>Gibt 2 Textwerte zurück, die den Verarbeitungsstatus für alle Ihre Dateien für einen ganzen Tag beschreiben: </p> 
    <ul id="ul_3FC092CA043A486C9C79FECF71FAF8FB"> 
     <li id="li_754B32D8267D44BBBD6EC354C459C566"> <code> ERFOLG</code> </li> 
     <li id="li_8B64E39C80424AC2B95DF9B53D62864E"> <code> FEHLER</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberFailure</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Dateien, die nicht erfolgreich verarbeitet wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> NumberSuccess</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der erfolgreich verarbeiteten Dateien. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimeRFC2822</code> </p> </td> 
   <td colname="col2"> <p>Gibt einen für Menschen lesbaren Zeitstempel für die Verarbeitung der Startzeiten zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimePOSIX</code> </p> </td> 
   <td colname="col2"> <p>Ein UNIX-Zeitstempel zur Verarbeitung der Startzeiten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Gesamtanzahl der Bytes für alle Metadatendateien des Tages. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Gesamtanzahl aller verarbeiteten Dateien für den Tag. </p> </td> 
  </tr> 
 </tbody> 
</table>
