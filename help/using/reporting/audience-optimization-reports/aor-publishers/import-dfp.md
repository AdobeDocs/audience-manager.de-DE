---
description: Bevor Audience Manager die Zielgruppenoptimierung für Herausgeber aktivieren kann, müssen Sie sicherstellen, dass alle Voraussetzungen, die in diesem Artikel beschrieben werden, erfüllt sind. Kontaktieren Sie die Kundenunterstützung, nachdem Sie sichergestellt haben, dass alle Voraussetzungen erfüllt sind.
seo-description: Bevor Audience Manager die Zielgruppenoptimierung für Herausgeber aktivieren kann, müssen Sie sicherstellen, dass alle Voraussetzungen, die in diesem Artikel beschrieben werden, erfüllt sind. Kontaktieren Sie die Kundenunterstützung, nachdem Sie sichergestellt haben, dass alle Voraussetzungen erfüllt sind.
seo-title: Importieren von DFP-Datendateien in Audience Manager
solution: Audience Manager
title: Importieren von DFP-Datendateien in Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '538'
ht-degree: 21%

---


# Importieren von DFP-Datendateien in Audience Manager{#import-dfp-data-files-into-audience-manager}

Bevor Audience Manager die Zielgruppenoptimierung für Herausgeber aktivieren kann, müssen Sie sicherstellen, dass alle Voraussetzungen, die in diesem Artikel beschrieben werden, erfüllt sind. Kontaktieren Sie die Kundenunterstützung, nachdem Sie sichergestellt haben, dass alle Voraussetzungen erfüllt sind.

## Voraussetzungen für die Aufnahme des DFP-Protokolls {#prereqs-dfp-ingestion}

Beachten Sie, dass der in diesem Abschnitt beschriebene Prozess abgeschlossen werden muss, *bevor* Sie zu den Voraussetzungen für die Aktivierung der Protokollerfassung wechseln.

Um DFP-Protokolldateien ( [!DNL DoubleClick For Publishers]) verwenden zu können, müssen [!DNL Audience Manager]Sie zunächst unsere UUID (Unique User ID) für den [Audience Manager im Tag-Aufruf (Ad-Tag-ID)](../../../reference/ids-in-aam.md) festlegen. Auf diese Weise ist unsere ID in den DFP-Protokollen enthalten und wir können IDs zwischen DFP und [!DNL Audience Manager]DFP abgleichen. Verwenden Sie [!DNL Audience Manager] Code oder den [!UICONTROL DIL] Code, um die [!UICONTROL Audience Management Module] [!DNL Audience Manager] UUID in einem Erstanbieter-Cookie festzulegen.

So legen Sie die [!DNL Audience Manager] ID im Tag-Aufruf fest, wie in unserer Dokumentation beschrieben:

* [Über Google Publisher Tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [Über ein Cookie-Ziel](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

Sie müssen die [!DNL Audience Manager] ID selbst festlegen und können mit [!DNL Audience Manager] Beratung prüfen, ob alles funktioniert. Sie haben die [!DNL Audience Manager] ID korrekt festgelegt, wenn:

* `'aamid'` ist der Schlüssel, der als Bezeichner verwendet wird.
* Der Benutzer-ID-Wert ist korrekt als [!DNL Audience Manager] UUID formatiert, wie in unserem [ID-Index in Audience Manager](../../../reference/ids-in-aam.md)beschrieben.
* Sie haben die [!DNL Audience Manager] UUID in ein definiertes Feld in Ihren DFP-Protokollen eingeschlossen (z. B. CustomTargeting).

## Voraussetzungen für die Protokollbereitstellung {#prereqs-ingestion-enablement}

<table id="table_C980A9F9B0FB4157B4908A64768B1571"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Schritt </th> 
   <th colname="col2" class="entry"> Details </th> 
   <th colname="col3" class="entry"> Inhaber </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Schritt 1 </p> </td> 
   <td colname="col2"> <p>Vergewissern Sie sich, dass die erforderlichen Schritte zum Festlegen der UUID für den <span class="keyword"> Audience Manager</span> (siehe oben) ausgeführt wurden, bevor Sie zu Schritt 2 wechseln. </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> -Kundenunterstützung oder -Beratung </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schritt 2 </p> </td> 
   <td colname="col2"> <p>Ihr DFP-Administrator erstellt: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Ein Dienstkonto zum Erfassen von DFP-Protokollen in <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Neue Anmeldeinformationen. <p>Hinweis:  Dies erfordert möglicherweise eine eindeutige E-Mail-Adresse, die für dieses Projekt spezifisch ist, und wird bei der Bereitstellung des Zugriffs auf das Google Datenspeicherung Bucket verwendet. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Ein privater Schlüssel (JSON-basierte Berechtigung) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Ihr DFP-Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schritt 3 </p> </td> 
   <td colname="col2"> <p>Ihr DFP-Administrator gewährt API-Zugriff auf das Dienstkonto. Dieser Schritt ermöglicht den Zugriff auf die Metadaten, um Dimensionen (Zeilenelemente, Bestellungen, kreative Elemente) zu definieren. <p>Hinweis:  Verwenden Sie den in Schritt 2 eingerichteten E-Mail-Zugriff auf das Dienstkonto, um Zugriff auf die API zu gewähren. </p> </p> </td> 
   <td colname="col3"> <p>Ihr DFP-Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schritt 4 </p> </td> 
   <td colname="col2"> <p>Ihr DFP-Administrator hat Zugriff auf das Google Datenspeicherung Bucket. Denken Sie daran: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Dies kann über eine Google-Gruppe erfolgen. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Verknüpfen Sie die eindeutige E-Mail-Adresse, die dem Dienstkonto zugewiesen ist, mit dem Behälter "Datenspeicherung". </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Ihr DFP-Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schritt 5 </p> </td> 
   <td colname="col2"> <p>Ihr DFP-Administrator stellt die DFP-Netzwerk-ID bereit. Auf diese Weise können wir die Netzwerk-ID bei Aufrufen an die API weitergeben. </p> </td> 
   <td colname="col3"> <p>Ihr DFP-Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schritt 6 </p> </td> 
   <td colname="col2"> <p>Kompilieren Sie die Voraussetzungen in einer E-Mail an die AAM-Kundenunterstützung (aamsupport@adobe.com), um den Protokollerfassungsprozess zu starten. Entwerfen Sie die E-Mail mit der Vorlage im nächsten Abschnitt. </p> </td> 
   <td colname="col3"> <p>Sie, oder <span class="keyword"> Audience Manager</span> Consulting in Ihrem Namen </p> </td> 
  </tr> 
 </tbody> 
</table>

## E-Mail-Vorlage {#email-template}

Um die Aktivierung der Protokollerfassung abzuschließen, senden Sie uns eine E-Mail an aamsupport@adobe.com. Bitte verwenden Sie die [beiliegende E-Mail-Vorlage](assets/enable_dfp_ingestion.txt).
