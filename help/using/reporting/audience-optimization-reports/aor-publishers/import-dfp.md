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
source-wordcount: '511'
ht-degree: 14%

---

# Importieren von Google Ad Manager-Datendateien (ehemals DFP) in Audience Manager{#import-dfp-data-files-into-audience-manager}

Bevor Audience Manager die Zielgruppenoptimierung für Herausgeber aktivieren kann, müssen Sie sicherstellen, dass alle Voraussetzungen, die in diesem Artikel beschrieben werden, erfüllt sind. Kontaktieren Sie die Kundenunterstützung, nachdem Sie sichergestellt haben, dass alle Voraussetzungen erfüllt sind.

## Voraussetzungen für die Google Ad Manager-Protokollaufnahme {#prereqs-dfp-ingestion}

Beachten Sie, dass der in diesem Abschnitt beschriebene Prozess abgeschlossen sein muss *bevor* Sie mit den Voraussetzungen für die Aktivierung der Protokollaufnahme fortfahren.

Um [!DNL Google Ad Manager] (früher Google DFP)-Protokolldateien in [!DNL Audience Manager] verwenden zu können, müssen Sie zunächst unsere [eindeutige Audience Manager-Benutzer-ID (UUID) ](../../../reference/ids-in-aam.md) den Tag-Aufruf der Anzeige festlegen. Auf diese Weise wird unsere ID in die [!DNL Google Ad Manager]-Protokolle aufgenommen, und wir können die IDs zwischen [!DNL Google Ad Manager] und [!DNL Audience Manager] abgleichen. Verwenden Sie [!DNL Audience Manager] [!UICONTROL DIL] oder den [!UICONTROL Audience Management Module], um die [!DNL Audience Manager] UUID in einem Erstanbieter-Cookie festzulegen.

So legen Sie die [!DNL Audience Manager]-ID im Aufruf des Anzeigen-Tags fest, wie in unserer Dokumentation erläutert:

* [Über Google Publisher Tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [Über ein Cookie-Ziel](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

Sie müssen die [!DNL Audience Manager]-ID selbst festlegen und können mit [!DNL Audience Manager] Consulting zusammenarbeiten, um zu überprüfen, ob alles funktioniert. Sie haben die [!DNL Audience Manager]-ID korrekt festgelegt, wenn:

* `'aamid'` ist der Schlüssel, der als Kennung verwendet wird.
* Der Wert der Benutzer-ID ist korrekt als [!DNL Audience Manager] UUID formatiert, wie in unserem [ID-Index in Audience Manager](../../../reference/ids-in-aam.md) beschrieben.
* Sie haben die [!DNL Audience Manager] UUID in ein definiertes Feld in Ihren [!DNL Google Ad Manager]-Protokollen (z. B. CustomTargeting) eingefügt.

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
   <td colname="col2"> <p>Bestätigen Sie, dass die erforderlichen Schritte zum Festlegen der <span class="keyword"> Audience Manager</span> UUID (siehe oben) ausgeführt wurden, bevor Sie mit Schritt 2 fortfahren </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> Kundenunterstützung oder Beratung </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schritt 2 </p> </td> 
   <td colname="col2"> <p>Ihr Google Ad Manager-Administrator erstellt: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Ein Service-Konto für die Aufnahme von Google Ad Manager-Protokollen in <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Neue Anmeldedaten. <p>Hinweis: Dies erfordert möglicherweise eine eindeutige projektspezifische E-Mail-Adresse und wird bei der Bereitstellung des Zugriffs auf den Google-Speicher-Bucket verwendet. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Ein privater Schlüssel (JSON-basierte Anmeldedaten) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Ihr Google Ad Manager-Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schritt 3 </p> </td> 
   <td colname="col2"> <p>Ihr Google Ad Manager-Administrator gewährt der API Zugriff auf das Service-Konto. Dieser Schritt ermöglicht den Zugriff auf die Metadaten, um Dimensionen (Zeilenelemente, Bestellungen, Kreative) abzugrenzen. <p>Hinweis: Verwenden Sie das Service-Konto E-Mail-Zugriff , das Sie in Schritt 2 eingerichtet haben, um Zugriff auf die API zu gewähren. </p> </p> </td> 
   <td colname="col3"> <p>Ihr Google Ad Manager-Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schritt 4 </p> </td> 
   <td colname="col2"> <p>Ihr Google Ad Manager-Administrator richtet den Zugriff auf den Google Storage Bucket ein. Denken Sie daran: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Dies kann über eine Google-Gruppe erfolgen. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Verknüpfen Sie die dem Service-Konto zugewiesene eindeutige E-Mail-Adresse mit dem Speicher-Bucket. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Ihr Google Ad Manager-Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schritt 5 </p> </td> 
   <td colname="col2"> <p>Ihr Google Ad Manager-Administrator stellt die Google Ad Manager-Netzwerk-ID bereit. Dadurch können wir bei Aufrufen an die -API die Netzwerk-ID übergeben. </p> </td> 
   <td colname="col3"> <p>Ihr Google Ad Manager-Administrator </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Schritt 6 </p> </td> 
   <td colname="col2"> <p>Kompilieren Sie die Voraussetzungen und öffnen Sie ein Support-Ticket, indem Sie die <a href="https://experienceleague.adobe.com/docs/customer-one/using/home.html"> Anweisungen (hier</a> befolgen, um den Prozess der Protokollaufnahme zu starten. </p> </td> 
   <td colname="col3"> <p>Sie oder <span class="keyword"> Audience Manager</span> Consulting in Ihrem Auftrag </p> </td> 
  </tr> 
 </tbody> 
</table>
