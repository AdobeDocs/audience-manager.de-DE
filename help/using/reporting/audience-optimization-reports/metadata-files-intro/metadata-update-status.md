---
description: Das Statusverzeichnis S3 enthält eine .info-Datei mit Erfolgs- und Fehlerinformationen zu Ihren hochgeladenen Dateien. Die Datei enthält JSON-formatierte Daten mit Statusergebnissen in einem -Array.
seo-description: The S3 status directory holds a .info file with success and failure information about your uploaded files. The file contains JSON-formatted data with status results in an array.
seo-title: Status Updates for Metadata Files
solution: Audience Manager
title: Statusaktualisierungen für Metadatendateien
uuid: 56a1e88a-41da-4d51-a21e-2be98cca7fa2
feature: Log Files
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 1%

---


# Statusaktualisierungen für Metadatendateien{#status-updates-for-metadata-files}

Im S3-Statusverzeichnis befindet sich eine `.info` mit Erfolgs- und Fehlerinformationen zu den hochgeladenen Dateien. Die Datei enthält JSON-formatierte Daten mit Statusergebnissen in einem -Array.

Der Inhalt der `.info`-Datei sieht in etwa wie im folgenden Beispiel aus.

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

## Schlüssel-Wert-Paare für Metadaten definiert {#key-value-pairs}

In den folgenden Tabellen werden die Schlüssel in den Abschnitten `Files` und `Summary` einer Metadatenstatusdatei aufgelistet und definiert.

**Schlüssel im Dateien-Array**

<table id="table_BF23C032FEFA446282E9364E85BE8C9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Schlüssel </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Description</code> </p> </td> 
   <td colname="col2"> <p>Enthält eine kurze Beschreibung der Gründe für fehlgeschlagene Verarbeitungsvorgänge. Dieses Feld ist leer, wenn die Verarbeitung erfolgreich war. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Dateigröße in Byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Die MD 5-Prüfsumme für die in Ihr <code> meta</code> hochgeladene Metadatendatei. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>Der Name der Metadatendatei, die in Ihr <code> meta</code> hochgeladen wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> MetadataType</code> </p> </td> 
   <td colname="col2"> <p>Der menschenlesbare Name für den Datentyp, den Ihre Datei enthält. Es basiert auf der untergeordneten ID in Ihrem Dateinamen. </p> <p>Siehe <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> für Metadatendateien</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Parent</code> </p> </td> 
   <td colname="col2"> <p>Der menschenlesbare Name für den Datentyp, den Ihre Datei enthält. Es basiert auf der übergeordneten ID in Ihrem Dateinamen. </p> <p>Siehe <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> für Metadatendateien</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Status</code> </p> </td> 
   <td colname="col2"> <p>Gibt zwei Textwerte zurück, die den Verarbeitungsstatus Ihrer Metadatendatei beschreiben: </p> 
    <ul id="ul_3814EBB6B42B4EB294B1ABA5782190B6"> 
     <li id="li_92AAECE7E9A44B1193A1D93ABBCE46B0"> <code> SUCCESS</code> </li> 
     <li id="li_3109F4E254374117A89CB989F221CB18"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Schlüssel im Zusammenfassungsobjekt**

<table id="table_C765A0CDBAA14A2FB5E0D38BDD1D292A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Schlüssel </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>Dateiverarbeitungsdatum im <code><i>yyyy-mm-dd</i></code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> GlobalStatus</code> </p> </td> 
   <td colname="col2"> <p>Gibt zwei Textwerte zurück, die den Verarbeitungsstatus für alle Dateien für einen ganzen Tag beschreiben: </p> 
    <ul id="ul_3FC092CA043A486C9C79FECF71FAF8FB"> 
     <li id="li_754B32D8267D44BBBD6EC354C459C566"> <code> SUCCESS</code> </li> 
     <li id="li_8B64E39C80424AC2B95DF9B53D62864E"> <code> FAILURE</code> </li> 
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
   <td colname="col2"> <p>Gibt einen für Menschen lesbaren Zeitstempel für die Verarbeitungsstartzeiten zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimePOSIX</code> </p> </td> 
   <td colname="col2"> <p>Ein UNIX-Zeitstempel für Verarbeitungsstartzeiten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>Gesamtzahl der Bytes für alle Metadatendateien des Tages. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Gesamtzahl aller Dateien, die für den Tag verarbeitet wurden. </p> </td> 
  </tr> 
 </tbody> 
</table>
