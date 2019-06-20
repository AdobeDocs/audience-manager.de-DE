---
description: Der S 3-Status-Ordner enthält eine.info mit Erfolgs- und Fehlerinformationen zu Ihren hochgeladenen Dateien. Die Datei enthält JSON-formatierte Daten mit Status in einem Array.
seo-description: Der S 3-Status-Ordner enthält eine.info mit Erfolgs- und Fehlerinformationen zu Ihren hochgeladenen Dateien. Die Datei enthält JSON-formatierte Daten mit Status in einem Array.
seo-title: Statusaktualisierungen für Metadatendateien
solution: Audience Manager
title: Statusaktualisierungen für Metadatendateien
uuid: 56 a 1 e 88 a -41 da -4 d 51-a 21 e -2 be 98 cca 7 fa 2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Statusaktualisierungen für Metadatendateien{#status-updates-for-metadata-files}

Der S 3-Status-Ordner enthält eine `.info` Datei mit Erfolgs- und Fehlerinformationen zu Ihren hochgeladenen Dateien. Die Datei enthält JSON-formatierte Daten mit Status in einem Array.

Der Inhalt Ihrer `.info` Datei sieht wie in diesem Beispiel aus.

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

## Metadaten-Schlüssel-Wert-Paare definiert {#key-value-pairs}

Die folgende Tabelle zeigt die Schlüssel in den `Files` Abschnitten und `Summary` Abschnitten einer Metadatenstatusdatei.

**Schlüssel im Dateiarray**

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
   <td colname="col2"> <p>Enthält eine kurze Beschreibung der Verarbeitung der Verarbeitung. Dieses Feld ist leer, wenn die Verarbeitung erfolgreich ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filebytesize</code> </p> </td> 
   <td colname="col2"> <p>Dateigröße in Byte. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>Die MD 5-Prüfsumme für die Metadatendatei, die in den <code> Metaordner</code> hochgeladen wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Filename</code> </p> </td> 
   <td colname="col2"> <p>Der Name der Metadatendatei, die in den <code> Metaordner</code> hochgeladen wurde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Metadatatype</code> </p> </td> 
   <td colname="col2"> <p>Der lesbare Name für den Datentyp, den Ihre Datei enthält. Es basiert auf der untergeordneten ID in Ihrem Dateinamen. </p> <p>Siehe <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Namenskonventionen für Metadatendateien</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Übergeordnetes Element</code> </p> </td> 
   <td colname="col2"> <p>Der lesbare Name für den Datentyp, den Ihre Datei enthält. Es basiert auf der übergeordneten ID in Ihrem Dateinamen. </p> <p>Siehe <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Namenskonventionen für Metadatendateien</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Status</code> </p> </td> 
   <td colname="col2"> <p>Gibt 2 Textwerte zurück, die den Verarbeitungsstatus Ihrer Metadatendatei beschreiben: </p> 
    <ul id="ul_3814EBB6B42B4EB294B1ABA5782190B6"> 
     <li id="li_92AAECE7E9A44B1193A1D93ABBCE46B0"> <code> SUCCESS</code> </li> 
     <li id="li_3109F4E254374117A89CB989F221CB18"> <code> FAILURE</code> </li> 
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
   <td colname="col2"> <p>Dateiverarbeitungsdatum im <code><i>Format jjjj-mm-tt</i></code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Globalstatus</code> </p> </td> 
   <td colname="col2"> <p>Gibt 2 Textwerte zurück, die den Verarbeitungsstatus für alle Ihre Dateien über einen ganzen Tag beschreiben: </p> 
    <ul id="ul_3FC092CA043A486C9C79FECF71FAF8FB"> 
     <li id="li_754B32D8267D44BBBD6EC354C459C566"> <code> SUCCESS</code> </li> 
     <li id="li_8B64E39C80424AC2B95DF9B53D62864E"> <code> FAILURE</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Numberfailure</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der Dateien, die nicht erfolgreich verarbeitet wurden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Numbersuccess</code> </p> </td> 
   <td colname="col2"> <p>Die Anzahl der erfolgreich verarbeiteten Dateien. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> ProcessingTimeRFC2822</code> </p> </td> 
   <td colname="col2"> <p>Gibt einen Menschen lesbaren Zeitstempel für die Verarbeitung von Startzeiten zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Processingtimeposix</code> </p> </td> 
   <td colname="col2"> <p>Ein UNIX-Zeitstempel für die Verarbeitung von Startzeiten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Totalbytesize</code> </p> </td> 
   <td colname="col2"> <p>Gesamtanzahl der Bytes für alle Metadatendateien des Tages. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Totalnumberfiles</code> </p> </td> 
   <td colname="col2"> <p>Gesamtanzahl aller für den Tag verarbeiteten Dateien. </p> </td> 
  </tr> 
 </tbody> 
</table>
