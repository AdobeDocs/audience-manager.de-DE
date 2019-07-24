---
description: Senden oder aktualisieren Sie Metadatendateien, indem Sie sie an einen speziellen Amazon S 3-Ordner für Ihr Audience Manager-Konto senden. In diesem Abschnitt finden Sie Informationen zu Bereitstellungs-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen.
seo-description: Senden oder aktualisieren Sie Metadatendateien, indem Sie sie an einen speziellen Amazon S 3-Ordner für Ihr Audience Manager-Konto senden. In diesem Abschnitt finden Sie Informationen zu Bereitstellungs-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen.
seo-title: Auslieferungsmethoden für Metadatendateien
solution: Audience Manager
title: Auslieferungsmethoden für Metadatendateien
uuid: 5199 ee 9 b -920 d -423 d -8070-05 a 017 ecd 62
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Delivery Methods for Metadata Files{#delivery-methods-for-metadata-files}

Senden oder aktualisieren Sie Metadatendateien, indem Sie sie an einen speziellen Amazon S 3-Ordner für Ihr Audience Manager-Konto senden. In diesem Abschnitt finden Sie Informationen zu Bereitstellungs-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen.

## Delivery Path Syntax and Examples {#syntax}

Die Daten werden für jeden Kunden in einem Amazon S 3-Ordner in einem separaten Namespace gespeichert. Der Dateipfad folgt der unten aufgeführten Syntax. Note, *italics* indicates a variable placeholder. Brackets `[ ]` indicate optional parameters. Die anderen Elemente sind Konstanten und ändern sich nicht.

**Syntax:**
<pre><code>…/log_ incapture/pid =<i>AAM ID</i>/dpid = <i>d_ src</i>/[meta | status]/ <i>yyyymmdd</i>_ <i>parent ID</i>_ <i>child ID</i></code></pre>

Die folgende Tabelle definiert alle diese Elemente in einem Dateibereitstellungspfad.

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dateiparameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> …/log_ incapture/</code> </p> </td> 
   <td colname="col2"> <p>Dies ist der Anfang des Ordnerspeicherpfades. Wenn alles eingerichtet ist, erhalten Sie den vollständigen Pfad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid =<i>AAM ID</i></code> </p> </td> 
   <td colname="col2"> <p>This key-value pair that contains your <span class="keyword"> Audience Manager</span> customer ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid =<i>d_ src</i></code> </p> </td> 
   <td colname="col2"> <p>Dieses Schlüssel-Wert-Paar enthält die Datenquellen-ID, die bei einem Ereignisaufruf weitergegeben wird. Die Datenquellen-ID ist der Wert, der alle Inhalte in Ihrer Datei mit den tatsächlichen Daten verknüpft, zu denen sie gehört. </p> <p>Beispiel: Sie haben ein kreatives Element mit der ID 123 und der Name "Advertiser Creative A" , da der Ereignisaufruf nur die ID durchläuft, um" Advertiser Creative A" in die Metadatendatei einzuschließen. Die Kampagne und kreative Elemente gehören zu einer Datenquelle. Die Datenquellen-ID verbindet diese gemeinsam und ermöglicht es uns, Dateiinhalte einer ID zuzuordnen, die in einem Ereignisaufruf gesendet wird. See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names"> How Event Call IDs Determine File Names, Contents, and Delivery Paths</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_8AFA4E7FCE984789AF05EA31718F39CD"> 
     <li id="li_A493880F6ECB467DBB590226CC7A5847"> <code> meta</code> </li> 
     <li id="li_2D6DAC956D084A1DB43C9C5B2C821F87"> <code> status</code> </li> 
    </ul> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_5907ADF5B20C4FEC94EF5A09BE02F2CD"> 
      <li id="li_AE70B44FEDCF4A05ADAFF4E49296F67D"> <code> meta</code> ist ein Datei-Upload-Ordner. </li> 
      <li id="li_2ADEA90E01364E888CAAAB8A65A6383F"> <code> status</code> ist ein Pfad zu einem Ordner, der Erfolgs- oder Fehlerinformationen zu Ihren verarbeiteten Dateien enthält. After your file is processed, you'll see a <code> .info</code> file with <code> yyyymmdd</code> timestamp title. Statusdateien enthalten Daten in einem JSON-Objekt. See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md"> Status Updates for Metadata Files</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code><i>JJJMMTT</i>_<i>parent ID</i>_<i>child ID</i></code> </p> </td> 
   <td colname="col2"> <p>Dies ist der Dateiname. See <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Naming Conventions for Metadata Files</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Beispielupload- und Statuspfade**

To upload a metadata file or to [check its status](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md), the file paths will look similar to these:

* Upload path: `/log_ingestion/pid=1234/dpid=567/meta/20150827_1_2`
* Processing status path: `/log_ingestion/pid=1234/dpid=567/status/20150827.info`.

## File Processing Times and Updates {#processing-times}

Metadatendateien werden viermal täglich verarbeitet.

Um Ihre Metadatensätze zu aktualisieren, senden Sie einfach eine Datei mit neuen Informationen. Sie müssen nicht jedes Mal vollständige Updates senden.
