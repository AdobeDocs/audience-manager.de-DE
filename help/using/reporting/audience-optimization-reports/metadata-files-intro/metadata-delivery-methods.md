---
description: Senden oder aktualisieren Sie Metadatendateien, indem Sie sie an einen speziellen Amazon S3-Ordner für Ihr Audience Manager-Konto senden. Informationen zu Bereitstellungs-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen finden Sie in diesem Abschnitt.
seo-description: Senden oder aktualisieren Sie Metadatendateien, indem Sie sie an einen speziellen Amazon S3-Ordner für Ihr Audience Manager-Konto senden. Informationen zu Bereitstellungs-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen finden Sie in diesem Abschnitt.
seo-title: Bereitstellungsmethoden für Metadatendateien
solution: Audience Manager
title: Bereitstellungsmethoden für Metadatendateien
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bereitstellungsmethoden für Metadatendateien{#delivery-methods-for-metadata-files}

Senden oder aktualisieren Sie Metadatendateien, indem Sie sie an einen speziellen Amazon S3-Ordner für Ihr Audience Manager-Konto senden. Informationen zu Bereitstellungs-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen finden Sie in diesem Abschnitt.

## Syntax und Beispiele für Bereitstellungspfad {#syntax}

Daten werden für jeden Kunden in einem Amazon S3-Ordner in einem separaten Namespace gespeichert. Der Dateipfad folgt der unten stehenden Syntax. Note, *italics* indicates a variable placeholder. Klammern `[ ]` geben optionale Parameter an. Die anderen Elemente sind Konstanten und bleiben unverändert.

**Syntax:**
<pre><code>.../log_ingestion/pid=<i>AAM ID</i>/dpid= <i>d_src</i>/[meta|status]/ <i>yyymmdd</i>_ <i>übergeordnete ID</i>_ <i>untergeordnete ID</i></code></pre>

In der folgenden Tabelle werden diese Elemente in einem Dateibereitstellungspfad definiert.

<table id="table_E3DB873D4CB3479AA7173838EB9898CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dateiparameter </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> .../log_ingestion/</code> </p> </td> 
   <td colname="col2"> <p>Dies ist der Anfang des Ordnerspeicherpfads. Sie erhalten den vollständigen Pfad, wenn alles eingerichtet ist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>pid=<i>AAM-ID</i></code> </p> </td> 
   <td colname="col2"> <p>Dieses Schlüssel-Wert-Paar, das Ihre <span class="keyword"> Audience Manager</span> -Kunden-ID enthält. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>dpid=<i>d_src</i></code> </p> </td> 
   <td colname="col2"> <p>Dieses Schlüssel-Wert-Paar enthält die Datenquelle-ID, die bei einem Ereignisaufruf weitergegeben wird. Die Datenquellen-ID ist der Wert, der den gesamten Inhalt Ihrer Datei mit den tatsächlichen Daten verknüpft, zu denen sie gehört. </p> <p>Angenommen, Sie haben ein kreatives Element mit der ID 123 und dem Namen "Werbetreibende Kreative A". Da ein Ereignisaufruf nur in der ID weitergegeben wird, müssen Sie "Werbetreibende Kreative A"in die Metadatendatei aufnehmen. Die Kampagne und das kreative Element gehören zu einer Datenquelle. Die Datenquellen-ID verbindet diese und ermöglicht es uns, Dateiinhalte exakt mit einer ID zu verknüpfen, die bei einem Ereignisaufruf gesendet wird. Siehe <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names"> Bestimmen von Dateinamen, Inhalten und Bereitstellungspfaden</a>durch Ereignisaufruf-IDs. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_8AFA4E7FCE984789AF05EA31718F39CD"> 
     <li id="li_A493880F6ECB467DBB590226CC7A5847"> <code> meta</code> </li> 
     <li id="li_2D6DAC956D084A1DB43C9C5B2C821F87"> <code> status</code> </li> 
    </ul> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_5907ADF5B20C4FEC94EF5A09BE02F2CD"> 
      <li id="li_AE70B44FEDCF4A05ADAFF4E49296F67D"> <code> meta</code> ist ein Datei-Upload-/Speicherordner. </li> 
      <li id="li_2ADEA90E01364E888CAAAB8A65A6383F"> <code> status</code> ist ein Pfad zu einem Verzeichnis, in dem Erfolgs- oder Fehlerinformationen zu Ihren verarbeiteten Dateien gespeichert sind. Nach der Verarbeitung der Datei wird eine <code> .info</code> -Datei mit dem <code> Titel yyymmdd</code> timestamp angezeigt. Statusdateien enthalten Daten in einem JSON-Objekt. Siehe <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md"> Statusaktualisierungen für Metadatendateien</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>yyymmdd</i>_<i>parent ID</i>_<i>child ID</i></code> </p> </td> 
   <td colname="col2"> <p>Dies ist der Dateiname. Siehe <a href="../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md"> Benennungsregeln für Metadatendateien</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Beispiel-Upload- und Statuspfade**

Um eine Metadatendatei hochzuladen oder deren Status[zu ](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-update-status.md)überprüfen, sehen die Dateipfade wie folgt aus:

* Upload-Pfad: `/log_ingestion/pid=1234/dpid=567/meta/20150827_1_2`
* Pfad zum Verarbeitungsstatus: `/log_ingestion/pid=1234/dpid=567/status/20150827.info`.

## Dateiverarbeitungszeiten und -aktualisierungen {#processing-times}

Metadaten-Dateien werden in regelmäßigen Abständen viermal am Tag verarbeitet.

Um Ihre Metadaten-Datensätze zu aktualisieren, senden Sie einfach eine Datei mit neuen Informationen. Sie müssen keine vollständigen Updates jedes Mal senden.
