---
description: Bevor Audience Manager die Zielgruppenoptimierung für Herausgeber aktivieren kann, müssen Sie sicherstellen, dass alle Voraussetzungen, die in diesem Artikel beschrieben werden, erfüllt sind. Kontaktieren Sie die Kundenunterstützung, nachdem Sie sichergestellt haben, dass alle Voraussetzungen erfüllt sind.
seo-description: Before Audience Manager can enable Audience Optimization for Publishers, you must ensure that all prerequisites outlined in this article are met. Contact Customer Care after checking off all prerequisites.
seo-title: Import Google Ad Manager Data Files Into Audience Manager
solution: Audience Manager
title: Importieren von Google Ad Manager-Datendateien in Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: Audience Optimization Reports
exl-id: 62b72dd1-e664-4c6a-8c0a-f7a662d62a47
source-git-commit: 7147091e6c253e8124f5f21a2251c1a76ac9d808
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 15%

---

# Importieren von Google Ad Manager-Datendateien (ehemals DFP) in Audience Manager{#import-dfp-data-files-into-audience-manager}

Bevor Audience Manager die Zielgruppenoptimierung für Herausgeber aktivieren kann, müssen Sie sicherstellen, dass alle Voraussetzungen, die in diesem Artikel beschrieben werden, erfüllt sind. Kontaktieren Sie die Kundenunterstützung, nachdem Sie sichergestellt haben, dass alle Voraussetzungen erfüllt sind.

## Voraussetzungen für die Protokollierung in Google Ad Manager {#prereqs-dfp-ingestion}

Beachten Sie, dass der in diesem Abschnitt beschriebene Prozess abgeschlossen werden muss. *before* Navigieren Sie zu den Voraussetzungen für die Aktivierung der Protokollierung.

Zur Verwendung [!DNL Google Ad Manager] (ehemals Google DFP) Protokolldateien in [!DNL Audience Manager], müssen Sie zunächst [Audience Manager Unique User ID (UUID)](../../../reference/ids-in-aam.md) im Anzeigen-Tag-Aufruf. Dadurch wird unsere ID in der Variablen [!DNL Google Ad Manager] -Protokolle und wir können IDs zwischen [!DNL Google Ad Manager] und [!DNL Audience Manager]. Verwendung [!DNL Audience Manager] [!UICONTROL DIL] oder [!UICONTROL Audience Management Module] , um [!DNL Audience Manager] UUID in einem Erstanbieter-Cookie.

Hier erfahren Sie, wie Sie die [!DNL Audience Manager] ID im Anzeigen-Tag-Aufruf, wie in unserer Dokumentation beschrieben:

* [Über Google Publisher Tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [Über ein Cookie-Ziel](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

Sie müssen die [!DNL Audience Manager] Identifizieren Sie sich selbst und können mit [!DNL Audience Manager] Beratung, um zu überprüfen, ob alles funktioniert. Sie haben die [!DNL Audience Manager] ID richtig, wenn:

* `'aamid'` ist der Schlüssel, der als Kennung verwendet wird.
* Der Benutzer-ID-Wert ist korrekt formatiert als [!DNL Audience Manager] UUID, wie in der [Index der IDs in Audience Manager](../../../reference/ids-in-aam.md).
* Sie haben die [!DNL Audience Manager] UUID in einem definierten Feld in Ihrer [!DNL Google Ad Manager] Protokolle (z. B. CustomTargeting).

## Voraussetzungen für die Aktivierung der Protokollaufnahme {#prereqs-ingestion-enablement}

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
   <td colname="col2"> <p>Bestätigen Sie, dass die erforderlichen Schritte zum Festlegen der <span class="keyword"> Audience Manager</span> UUID (oben beschrieben) wurde vor dem Wechsel zu Schritt 2 abgeschlossen. </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> Kundenunterstützung oder Beratung </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schritt 2 </p> </td> 
   <td colname="col2"> <p>Ihr Google Ad Manager-Administrator erstellt: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Ein Dienstkonto für die Aufnahme von Google Ad Manager-Anmeldungen bei <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Neue Anmeldeinformationen. <p>Hinweis: Dies erfordert möglicherweise eine für dieses Projekt spezifische eindeutige E-Mail-Adresse und wird bei der Bereitstellung des Zugriffs auf den Google Storage Bucket verwendet. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Ein privater Schlüssel (JSON-basierte Berechtigung) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Ihr Google Ad Manager-Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schritt 3 </p> </td> 
   <td colname="col2"> <p>Ihr Google Ad Manager-Administrator gewährt der API Zugriff auf das Dienstkonto. Dieser Schritt ermöglicht den Zugriff auf die Metadaten, um Dimensionen (Zeileneinträge, Bestellungen, kreative Elemente) zu trennen. <p>Hinweis: Verwenden Sie den E-Mail-Zugriff für das Dienstkonto, den Sie in Schritt 2 eingerichtet haben, um Zugriff auf die API zu gewähren. </p> </p> </td> 
   <td colname="col3"> <p>Ihr Google Ad Manager-Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schritt 4 </p> </td> 
   <td colname="col2"> <p>Ihr Google Ad Manager-Administrator stellt Zugriff auf den Google-Speicher-Bucket her. Denken Sie daran: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Dies kann über eine Google-Gruppe erfolgen. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Verknüpfen Sie die eindeutige E-Mail-Adresse, die dem Dienstkonto zugewiesen ist, mit dem Speicher-Bucket. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Ihr Google Ad Manager-Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schritt 5 </p> </td> 
   <td colname="col2"> <p>Ihr Google Ad Manager-Administrator stellt die Google Ad Manager-Netzwerk-ID bereit. Auf diese Weise können wir die Netzwerk-ID übergeben, wenn wir Aufrufe an die API durchführen. </p> </td> 
   <td colname="col3"> <p>Ihr Google Ad Manager-Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schritt 6 </p> </td> 
   <td colname="col2"> <p>Kompilieren Sie die Voraussetzungen und öffnen Sie ein Support-Ticket, indem Sie die Anweisungen befolgen. <a href="https://experienceleague.adobe.com/docs/customer-one/using/home.html">here</a> , um den Prozess der Protokollaufnahme zu starten. </p> </td> 
   <td colname="col3"> <p>Sie oder <span class="keyword"> Audience Manager</span> Beratung in Ihrem Namen </p> </td> 
  </tr> 
 </tbody> 
</table>
