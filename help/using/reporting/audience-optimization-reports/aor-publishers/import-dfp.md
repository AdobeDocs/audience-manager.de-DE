---
description: Bevor Audience Manager die Zielgruppenoptimierung für Herausgeber aktivieren kann, müssen Sie sicherstellen, dass alle Voraussetzungen, die in diesem Artikel beschrieben werden, erfüllt sind. Kontaktieren Sie die Kundenunterstützung, nachdem Sie sichergestellt haben, dass alle Voraussetzungen erfüllt sind.
seo-description: Bevor Audience Manager die Zielgruppenoptimierung für Herausgeber aktivieren kann, müssen Sie sicherstellen, dass alle Voraussetzungen, die in diesem Artikel beschrieben werden, erfüllt sind. Kontaktieren Sie die Kundenunterstützung, nachdem Sie sichergestellt haben, dass alle Voraussetzungen erfüllt sind.
seo-title: Importieren von DFP-Datendateien in Audience Manager
solution: Audience Manager
title: Importieren von DFP-Datendateien in Audience Manager
uuid: c 685 f 34 f -3 e 50-4 c 4 b -99 fa-d 8 bbafe 0 b 268
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Importieren von DFP-Datendateien in Audience Manager{#import-dfp-data-files-into-audience-manager}

Bevor Audience Manager die Zielgruppenoptimierung für Herausgeber aktivieren kann, müssen Sie sicherstellen, dass alle Voraussetzungen, die in diesem Artikel beschrieben werden, erfüllt sind. Kontaktieren Sie die Kundenunterstützung, nachdem Sie sichergestellt haben, dass alle Voraussetzungen erfüllt sind.

## Voraussetzungen für die Erfassung von DFP-Protokollen {#prereqs-dfp-ingestion}

Beachten Sie, dass der in diesem Abschnitt beschriebene Prozess abgeschlossen *sein muss, bevor* Sie die Voraussetzungen für die Erfassung der Protokollerfassung übernehmen.

Zur Verwendung von DFP ( [!DNL DoubleClick For Publishers])-Protokolldateien [!DNL Audience Manager]müssen Sie zuerst unsere UUID [(Unique User ID) für Audience Manager](../../../reference/ids-in-aam.md) im Ad-Tag-Aufruf festlegen. Dazu ist unsere ID in DFP-Protokollen enthalten und wir können IDs zwischen DFP und [!DNL Audience Manager]. Verwenden [!DNL Audience Manager][!UICONTROL DIL] Sie Code oder den [!UICONTROL Audience Management Module] , um [!DNL Audience Manager] die UUID in einem Erstanbieter-Cookie festzulegen.

So legen Sie die [!DNL Audience Manager] ID im Anzeigentag-Aufruf fest, wie in unserer Dokumentation beschrieben:

* [Über Google Publisher Tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
* [Über ein Cookie-Ziel](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)

Sie müssen die [!DNL Audience Manager] ID selbst festlegen und [!DNL Audience Manager] mit Beratung arbeiten, um zu prüfen, ob alles funktioniert. Sie haben die [!DNL Audience Manager] ID korrekt festgelegt, wenn:

* `'aamid'` ist der Schlüssel, der als Bezeichner verwendet wird.
* Der Wert des Benutzer-ID wird korrekt als [!DNL Audience Manager] UUID formatiert, wie in unserem [Index von IDs in Audience Manager beschrieben](../../../reference/ids-in-aam.md).
* Sie haben die [!DNL Audience Manager] UUID in ein definiertes Feld Ihrer DFP-Protokolle eingebunden (z. B. customtargeting).

## Voraussetzungen für die Erfassung von Protokollierung {#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p>Überprüfen Sie, ob die erforderlichen Schritte zum Festlegen der <span class="keyword"> UUID für Audience Manager</span> (oben beschrieben) abgeschlossen wurden, bevor Sie zu Schritt 2 wechseln. </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> -Kundenunterstützung oder Consulting </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schritt 2 </p> </td> 
   <td colname="col2"> <p>Ihr DFP-Administrator erstellt: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Ein Dienstkonto zum Erfassen von DFP-Protokollen in <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Neue Anmeldeinformationen. <p>Hinweis: Dies kann eine eindeutige E-Mail-Adresse für dieses Projekt erfordern und wird verwendet, wenn der Zugriff auf den Google Storage Bucket erfolgt. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Ein privater Schlüssel (JSON-basierte Berechtigung) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Ihr DFP-Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schritt 3 </p> </td> 
   <td colname="col2"> <p>Ihr DFP-Administrator gewährt API-Zugriff auf das Dienstkonto. Dieser Schritt ermöglicht den Zugriff auf die Metadaten, um Dimensionen (Zeilenelemente, Bestellungen, kreative Elemente) zu trennen. <p>Hinweis: Verwenden Sie den E-Mail-Zugriff des Diensts, den Sie in Schritt 2 eingerichtet haben, um den Zugriff auf die API zu gewähren. </p> </p> </td> 
   <td colname="col3"> <p>Ihr DFP-Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schritt 4 </p> </td> 
   <td colname="col2"> <p>Ihr DFP-Administrator stellt Zugriff auf den Google Storage Bucket ein. Denken Sie daran: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Dies kann über eine Google-Gruppe durchgeführt werden. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Verknüpfen Sie die eindeutige E-Mail-Adresse, die dem Dienstkonto zugewiesen ist, dem Speicherbehälter. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Ihr DFP-Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schritt 5 </p> </td> 
   <td colname="col2"> <p>Ihr DFP Administrator stellt die DFP-Netzwerk-ID bereit. Auf diese Weise können wir die Netzwerk-ID weiterreichen, wenn Sie die API aufrufen. </p> </td> 
   <td colname="col3"> <p>Ihr DFP-Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schritt 6 </p> </td> 
   <td colname="col2"> <p>Kompilieren Sie die Voraussetzungen in einer E-Mail an AAM-Kundenunterstützung (aamsupport@adobe.com), um den Protokollvorgang für die Protokollierung zu starten. Entwurf der E-Mail mit der Vorlage im nächsten Abschnitt. </p> </td> 
   <td colname="col3"> <p>Sie oder <span class="keyword"> Audience Manager</span> Consulting in Ihrem Namen </p> </td> 
  </tr> 
 </tbody> 
</table>

## E-Mail-Vorlage {#email-template}

Um die Erfassung der Protokollerfassung abzuschließen, senden Sie uns eine E-Mail an aamsupport@adobe.com. Bitte verwenden [Sie die angehängte E-Mail-Vorlage](assets/enable_dfp_ingestion.txt).
